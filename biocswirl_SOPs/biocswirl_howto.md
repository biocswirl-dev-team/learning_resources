---
title: "BiocSwirl How to (messy version)"
author: "juphilip"
date: "5/14/2022"
output: html_document
---



### Setting up your environment
* install swirl and swirlify

### Setting up to write / test a course
* `library(swirlify)`
* `get_current_lesson()` will show you which lesson you're working on or open the dialogue box to select a YAML file to work on
* `set_lesson(path_to_yaml=)` also lets you set which lesson you want to work on.

### How to start writing a new course

### How to write a lesson
* http://swirlstats.com/swirlify/introduction.html
* set a lesson with `set_lesson()`
* add a new question template to the bottom of the yaml file by typing `wq_` in the console. wq is for write question. after the underscore hit tab to see the different options. E.g. one of the most used questions is a command question, wchih can be added with `wq_command()`. Make sure that your yaml file is saved before you add a new question or you might lose your progress.
* saving and using `wq_` might be a little tedious but it ensures the proper formatting of the questions
* alternatively you can copy the templates from the different questions from below. However this is more error prone, especially when it comes to answer testing


### Testing a course locally
* there are multiple steps to it (this will likely change with CI/CD)
* first using `test_course()` this will check each lesson for all necessary files and formatting and that each question has an answer and hint
* instead of `test_course()`, you can use `test_lesson()` to test individual (or the current) lesson. They will be tested in the same way as with `test_course()`
* after those tests, it is important to demo the lesson like they would work for a course taker. It's less overwhelming to start with one lesson at a time using `demo_lesson()`, You can also jump to a specific question using `demo_lesson(from = )`. this is very helpful when you're looking for a specific question as it might have come up during testing
* `demo_lesson()`
* `demo_course()`


#### Typical errors during test_course()
* `incomplete final line found on 'MANIFEST'` -> add additional line and save
* `Please provide a value for the Hint key in question 66.` -> not technically an error but indicates that hint is missing
* `Error in yaml.load(readLines(con), error.label = error.label, ...) : (lab05_data_visualization/lesson.yaml) Scanner error: mapping values are not allowed in this context at line 241, column 138` -> most likely a colon that hasn't been escaped -> /: is not sufficient in yaml. Easiest is to use double quotation marks around the whole question text.
* not so typical error: the variable y might be interpreted as 'yes' by swirl. I had some issues with that during AnswerTesting and having swirl auto-answer when using skip(). So maybe avoid using the variable y.
  
## Sharing / packing a course
* In order for someone else to take the course or even to properly demo, you have to pack the course into a *.swc file (SWirl Course file). This file can then be shared with other users and used to install the course on their computer/ in their R studio.
* use `set_lesson()` to set the lesson to any lesson within the course that you want to share and then use `pack_course` to create the .swc file. Your .swc file will appear in the same directory as the directory that contains the course folder. You also have the option to export the .swc file to another directory by specifying the export_path argument.
* make sure to include these files in your git commits and update them with `pack_course()` if you made changes to the lessons.

## Including a course in the BiocSwirl R package

## Installing a course (e.g. for testing/ demoing purposes)
* `library(swirl)`
* start swirl env with `swirl()`
* `swirl::install_course(swc_path = "/path/to/course.swc")`