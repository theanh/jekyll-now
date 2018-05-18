---
layout: post
title: Symfony BDD
---
Running a test, we need following things
+ Test case.
+ Sample data.


#### Required bundle
`symfony/symfony`  
`behat/behat`  
`behat/symfony2-extension`

#### Assert functions
`phpunit/phpunit`

#### Create sample data
`doctrine/data-fixtures`  
`nelmio/alice`  
`rezzza/alice-extension`

#### Http client
`guzzlehttp/guzzle`

#### Behat configuration
http://behat.org/en/latest/user_guide/configuration.html

#### Creating features
`tests/features/blabla.feature`
+ Sample content
```
Feature: Login
  In order to use the app
  As an API client
  I need to log in

  Background:
    Given I load "users" fixtures

  Scenario: Login
    Given I have the payload
      """
      {
        "username": "username",
        "password" : "password"
      }
      """
    When I request "request_type your_api"
    Then the response status code should be 200
    And the "data" property should exist
    And the "ok" property should be a boolean equalling "true"
```

#### Running test
`vendor/bin/behat`

#### Seeing Behat Sentences
`vendor/bin/behat -dl`

#### References
Please check the following link out for further information.  
https://knpuniversity.com/screencast/rest/testing  
https://github.com/rezzza/alice-extension
