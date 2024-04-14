# Track the Environmental Impact of Your Python Algorithms with CodeCarbon

Are you concerned about the environmental impact of your machine learning and data processing algorithms? This project demonstrates how to use the CodeCarbon library to track the energy consumption and carbon emissions of your Python programs.

## What is CodeCarbon?

CodeCarbon is a lightweight Python library that tracks the energy consumption and carbon emissions of a Python program. It does this by periodically measuring the power usage of the underlying hardware, including CPUs, GPUs, and RAM. CodeCarbon then calculates the total carbon emissions based on the carbon intensity of the local electricity grid, which it obtains from public data sources on the energy mix of different regions and cloud providers.

## Installation

To get started, install the CodeCarbon library using pip:

```
pip install codecarbon
```

## Usage

In the `main.ipynb` file, there is an example that shows how to integrate CodeCarbon into your Python code. Basically, you should follwo these steps

1. Confiure the `EmissionTracker` class

```python
# Configure CodeCarbon
import logging
from codecarbon import EmissionsTracker

tracker = EmissionsTracker(
    project_name="3CABTP",
    log_level=logging.INFO,
    output_file="model.csv",
    output_dir='./emissions/',
    save_to_file=True,
    measure_power_secs=5
)
```
2. Wrap the code that does the processing between the `start` and `stop` methods.

```python
tracker.start()

# Start your algorithm

tracker.stop()
```

3. The emissions data is saved to a CSV file in the `./emissions/` directory.


## Useful Links

- [CodeCarbon Documentation](https://mlco2.github.io/codecarbon/)
- [CodeCarbon GitHub Repository](https://github.com/mlco2/codecarbon)
- [Emissions Tracking Output Documentation](https://mlco2.github.io/codecarbon/output.html)

## Conclusion

By using CodeCarbon, you can gain insights into the environmental impact of your Python algorithms and make informed decisions about optimizing their efficiency. This is an important step towards building more sustainable and eco-friendly software solutions.