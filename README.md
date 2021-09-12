# pytest-learning

## pytest cli execution

pytest  -s print to screen
pytetst -s -v verbose print tp screen

## using pychram configuration to run pytest
pytest target and working directory
python integrated tools --> pytest instead of unittest 
now able to use arrows to run specific test

## test fixtures

def setup_function(function):
def teardown_function(function):

def setup_module(module):
def teardown_module(module):

## fixtures decoraters
@pytest.fixture(scope='function')
def before():

yield --> acts like after

def test_dologin(before):
or
@pytest.mark.usefixtures("setup", "before")
def test_login():

## running specific test using 
pytest test_first_testcase.py -s -v -k login

pytest test_first_testcase.py -s -v -k "not login"

## using markers
@pytest.mark.regression
pytest test_first_testcase.py -s -v -m regression
how to register markers using ini file
@pytest.mark.skip

## parametrized test 
@pytest.mark.parametrize("username", "password", get_data())

## assertion

asset exceprted == actual, "what happen if failed"
assert "gmail" in Title, "gmail does not exist"
assert False , "make the test fail forcefully"

## pytest-soft-assertion 
inorder to use mulitple assertions
pytest test_first_testcase.py -s -v --soft-asserts
