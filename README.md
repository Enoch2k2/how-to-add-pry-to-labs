# How to add pry to labs

Make sure to have already opened a lab and are in the right directory in your terminal. It should say the lab name in the terminal.

## Installing Pry

#### Step 0: IF GEMFILE exists and already contains pry, skip to step:3, if pry is not inside the GEMFILE, skip to step 2

#### Step 1: Create a Gemfile by running in the terminal
```
bundle init
```

A GEMFILE should appear.

#### Step 2: Add pry as a dependency in your GEMFILE

Inside your GEMFILE after:
```
source "https://rubygems.org"

git_source(:github) {|repo_name| "https://github.com/#{repo_name}" }
```

add this line:
```
gem 'pry'
```

#### Step 3: Install dependencies

To install pry we will need to run:
```
bundle install
```

This will install all the dependencies in our GEMFILE

#### Step 4: Load pry inside of file you are working in.

In the top of the file you are coding in add:

```
require 'pry'
```

This will load pry into our file to be able to be used.


#### Step 5: Add your binding and using pry
Wherever you would like code to freeze at and start pry make sure to add a `binding.pry`. For example:

```
def add_two_nums_and_divide_by_2(a, b)
  result = a + b
  binding.pry
  result / 2
end
```

Here the result variable, a, and b will all be defined, however result / 2 would not be defined. It will open a pry session in the terminal as soon as `add_two_nums_and_divide_by_2` is called.

#### Step 6: Exiting Pry
With pry there are two ways to exit pry.

The first way is exiting one binding.pry to be able to hit another binding.pry. We do this with typing `exit`.

If you want to exit pry completely without going to anymore binding.pry's. You would type `exit!`.
