# learn-pydantic

[Link to the Pydantic documentation](https://docs.pydantic.dev/latest/)

- Data validation library for python

```python
from datetime import datetime
from typing import Tuple

from pydantic import BaseModel


class Delivery(BaseModel):
    timestamp: datetime
    dimensions: Tuple[int, int]


m = Delivery(timestamp='2020-01-02T03:04:05Z', dimensions=['10', '20'])
print(repr(m.timestamp))
#> datetime.datetime(2020, 1, 2, 3, 4, 5, tzinfo=TzInfo(UTC))
print(m.dimensions)
#> (10, 20)
```

## Why use Pydantic?

- powered by typhints
  - schema validation and serialization are controlled by type annotations
    - less to learn, less code to write, and integration with IDE
- fast
  - core logic written in Rust
- JSON Schema
  - built in support for generating JSON Schema
- Strict and lax mode
  - strict: data is not converted
  - lax: pydantic tries to coerce data to the correct type where appropriate
- Dataclasses, TypedDict and more
  - pydantic can be used for validating via many standard library types
- Customisation
  - pydantic allows custom validators and serializers to alter how data is processed in many powerful ways
