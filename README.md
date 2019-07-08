# fakelogs

## General
This library can be used to generate a high volume of fake logs in multiple formats.  It uses the [Faker](https://faker.readthedocs.io/en/master/) library for generating the data.  It currently only supports logging to stdout with the main goal of running it in a pod.

## Install
```bash
pip install fakelogs 
#or 
make install 
#or 
python setup.py install
```

## Configuration
Environment variables are used to configure the output of this program:
1. OUTPUT_FORMAT - This is the format used to output the fake data.  3 options are supported currently:
   * text - This generates a very basic log line with random text (Faker.text). (default)
   * kv - This generates a log with fake user profile data (Faker.profile) using a key/value pair format.
   * json - This generates a log with fake user profile data (Faker.profile) using a json format
2. TIME_TO_SLEEP: This is the time to sleep in seconds between each data generation (default is 1 second)
3. RECORDS_PER_ITERATION: This is the number of log records that should be generated before sleeping. (default is 1)

## Usage
```bash
export OUTPUT_FORMAT=json
export TIME_TO_SLEEP=1
export RECORDS_PER_ITERATION=10
fakelogs
```
