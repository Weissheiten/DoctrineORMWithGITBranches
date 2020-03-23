# Working with DoctrineORM and GIT feature branches

## Setting
2 developers - Kassandra and Mike - would like to work together on a project. They already know:
- how to use GIT for version control
- how to use composer for PHP projects
- the basic functionality of Doctrine ORM

Both developers are going to use a personal environment hosted on their local computer. As a Version Control System in itself does not manage their respective databases however, they want to make sure they have the same database structure after developing their respective features.
- Kassandra is going to write the code for a User
- Mike is going to write the code for a Product

Both developers have prepared a common setup from where to start.

## Kassandra writes the User class
Kassandra starts by cloning the repository at https://github.com/Weissheiten/DoctrineORMWithGITBranches.git and checks out the master branch.

```git checkout master```

This is the common ground from which both developers start, but she wants to make sure, that her changes don't interfere with the changes of Mike while working on the project.. Therefore she starts a so called "feature branch" and names it after the job she's performing:

``` git checkout -b IntroduceUser ```

Mike does the same and introduces his own feature branch with:

``` git checkout -b IntroduceProduct```

*In our example you don't have to create an own feature branch, this is only documented to show how it would be done.*

Both developers now work on their own feature branch, making changes and committing them. This does not interfer with any of the work the other developer does. Kassandra can concentrate on Users, while Mike can concentrate on the Products.

Both developers can use common doctrine commands to create their own database structure while developing like:
``` vendor/bin/doctrine orm:schema-tool:update --force --dump-sql ```

## Links

Doctrine ORM - Getting started:
https://www.doctrine-project.org/projects/doctrine-orm/en/current/tutorials/getting-started.html
