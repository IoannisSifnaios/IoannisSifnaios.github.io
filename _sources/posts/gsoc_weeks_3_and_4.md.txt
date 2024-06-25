# Google Summer Of Code 2024 - Weeks 3 and 4
```{post} 2024-06-24
:author: Ioannis Sifnaios
:tags: pvlib, github, open science, gsoc
```

So GSoC goes on strong, and almost one month has passed since the start of the coding period! I have to admit that I feel much more comfortable with [GitHub](https://github.com/) and the structure of [pvlib](https://github.com/pvlib/pvlib-python), which really makes a difference in progressing with my GSoC tasks. Of course, the main reason is the incredible amount of help I have received from my mentors [Adam R. Jensen](https://github.com/AdamRJensen) and [Kevin Anderson](https://github.com/kandersolar), but also from my fellow GSoC students [Echedey Luis](https://github.com/echedey-ls) and [Rajiv Daxini](https://github.com/RDaxini). Overall, my GSoC experience proves just how strong the open science community is and how willing people are to assist even newbie programmers who have many questions.

Over the last two weeks, I actually achieved my first big milestone; I got two of my PRs merged into the main pvlib code (yay!). The new release of pvlib ([v0.11.0](https://pvlib-python.readthedocs.io/en/stable/whatsnew.html)) was announced on June 21<sup>st</sup>, and I am so happy to see my name in the contributors' list!

One of the things I recently spent more time on was function tests. Honestly, it feels like this is where magic happens... I feel like the more sophisticated the topics, the less intuitive the commands are! So, I can't really say that I understand exactly why things are working, but they do! Thus, I will try to share what I've understood so far...

Pvlib's tests are done using pytest. Pytest is a popular testing framework for Python that allows developers to write simple and scalable test cases for their code. It provides a robust set of tools to ensure code quality and reliability. Pytest can handle everything from simple unit tests to complex functional and integration tests. So far, I have only used fixtures and parametrized tests.

Fixtures in pytest are functions that can set up the necessary state or context for tests, making it easier to manage setup and teardown tasks. They are reusable and can be used to provide a consistent test environment. For example, in the code below, I used fixtures to define a reusable setup function that can be used across multiple test functions, thus making the test code cleaner and more modular.

```
@pytest.fixture
def times():
    return pd.date_range(start="2015-01-01 00:00", end="2015-01-07 00:00", freq="1d")

@pytest.fixture
def air_temps(times):
    return pd.Series([-15, -5, 2.5, 15, 20, 30, 40], index=times)

@pytest.fixture
def water_temps_expected(times):
    return pd.Series([np.nan, 1.25, 6.875, 16.25, 20, 27.5, 35], index=times)

def test_stream_temperature_stefan_ndarray(air_temps, water_temps_expected):
    result = floating.stream_temperature_stefan(temp_air=air_temps.to_numpy())
    assert_allclose(water_temps_expected.to_numpy(), result)

def test_stream_temperature_stefan_series(air_temps, water_temps_expected):
    result = floating.stream_temperature_stefan(temp_air=air_temps)
    assert_series_equal(water_temps_expected, result)
```

Apart from fixtures, I also used parameterized tests. Parametrized tests in pytest allow you to run a single test function with multiple sets of parameters, enhancing your ability to efficiently test different inputs and scenarios. This helps in reducing redundancy and improving test coverage. In the example below, I check if passing the value on the left (e.g., -5) returns the value on the right (e.g., 1.25).

```
@pytest.mark.parametrize('air_temp,water_temp', [
    (-15, np.nan),
    (-5, 1.25),
    (40, 35),
])
def test_stream_temperature_stefan(air_temp, water_temp):
    result = floating.stream_temperature_stefan(air_temp)
    assert_allclose(result, water_temp)
```

Tests are used to ensure that the functions that we add to pvlib work as expected. It is thus crucial to include all "extreme" cases that could occur in the tests and test potential warning and error messages.

The progress of my project is described in [this issue](https://github.com/pvlib/pvlib-python/issues/2068). Stay tuned for updates!
