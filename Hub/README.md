# Selenium Grid Hub

The Hub receives a test to be executed along with information on which browser and 'platform' where the test should be run. The hub will use this information and delegate to a node that can service those needs.

## Dockerfile

[`selenium/hub` Dockerfile](Dockerfile)

## How to use this image

```
$ docker run -d -p 4444:4444 --name selenium-hub selenium/hub
```

Note: You can optionally override default configuration settings using environment variables.
See the [Hub's Dockerfile](Dockerfile) to view the list of variables and their default values.

```
$ docker run -d -p 4444:4444 --name selenium-hub -e GRID_TIMEOUT=10 selenium/hub
```


Once the hub is up and running will want to launch nodes that can run tests. You can run as many nodes as you wish.

```
$ docker run -d --link selenium-hub:hub -v /dev/shm:/dev/shm selenium/node-chrome
$ docker run -d --link selenium-hub:hub -v /dev/shm:/dev/shm selenium/node-firefox
```

## What is Selenium?
_Selenium automates browsers._ That's it! What you do with that power is entirely up to you. Primarily, it is for automating web applications for testing purposes, but is certainly not limited to just that. Boring web-based administration tasks can (and should!) also be automated as well.

Selenium has the support of some of the largest browser vendors who have taken (or are taking) steps to make Selenium a native part of their browser. It is also the core technology in countless other browser automation tools, APIs and frameworks.

See the Selenium [site](https://www.selenium.dev/documentation/en/) for documentation on usage within your test code.

## License

View [license information](../LICENSE.md) for the software contained in this image.

## Getting Help

### User Group

The first place where people ask for help about Selenium is the [Official User Group](https://groups.google.com/forum/#!forum/selenium-users). Here, you'll find that most of the time, someone already found the problem you are facing right now, and usually reached the solution for which you are looking.

_Note: Please make sure to search the group before asking for something. Your question likely won't get answered if it was previously answered in another discussion!_

### Chat Room

The best place to ask for help is the user group (because they also keep the information accessible for others to read in the future). However, if you have a very important (or too simple) issue that needs a solution ASAP, you can always enter the IRC chat room. You might just find someone ready to help on `#selenium` at [Freenode](https://freenode.net/) or [SeleniumHQ Slack](https://seleniumhq.herokuapp.com/)

### Issues

If you have any problems with or questions about this image, please contact us through a [Github issue](https://github.com/SeleniumHQ/docker-selenium/issues). If you have any problems with or questions about Selenium, please contact us through Selenium's [Bug Tracker](https://github.com/SeleniumHQ/selenium/issues).

## Contributing

There are many ways to [contribute](https://www.selenium.dev/getinvolved/) whether by answering user questions, additional docs, or pull request we look forward to hearing from you.

If you do supply a patch we will need you to [sign the CLA](https://spreadsheets.google.com/spreadsheet/viewform?hl=en_US&formkey=dFFjXzBzM1VwekFlOWFWMjFFRjJMRFE6MQ#gid=0). We are part of [SFC](http://www.sfconservancy.org/)
