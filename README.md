
from phoenix.otel import register
import os
os.environ["PHOENIX_API_KEY"] = ""
os.environ["PHOENIX_COLLECTOR_ENDPOINT"] = ""
tracer_provider = register(
  project_name="Travel_Planner", # Default is 'default'
  auto_instrument=True, # See 'Trace all calls made to a library' below
)
tracer = tracer_provider.get_tracer(__name__)

@tracer.chain
