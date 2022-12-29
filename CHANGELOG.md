# Changelog

## 2022-12-02

- Bumped the version of Flower in runtime image to 1.1.0. This includes improvements such as better error logging when running simulated federated learning. See [Flower changelog](https://flower.dev/docs/changelog.html#v1-1-0-2022-10-31) for full details.
- Added example submission code. These are meant to be simple demonstrations of how to write code that works with evaluation harness. They do not meaningfully model the machine learning task nor do they implement any privacy techniques or technologies.
    - Added simple example submission for Track A: Financial Crime Prevention ([`examples_src/fincrime`](src/fincrime/)). This is a simplistic, dummy model that illustrates a heterogeneous sequence of client–server communications using the federated training and test simulations.
    - Added simple example submission for Track B: Pandemic Forecasting ([`examples_src/pandemic`](src/pandemic/)). This is a simplistic, naive model inspired by the SIR epidemiological model.
- Removed limitations on use the `fit` method on clients during the test inference simluation. This allows the use of the `fit` method, whose API better supports sending NumPy arrays to the server than the `evaluate` method, as part of test inference workflows. Note that use of the `fit` method is only meant to facilitate client–server communications. Solutions should _not_ be fitting models on the test data during the test inference.
