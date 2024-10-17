Gator CLI - A Multi-user Command-Line Application

Introduction

Gator is a multi-user command-line application that allows you to interact with RSS feeds in a simple and intuitive way. You can register new users, follow feeds, and browse posts, all from the comfort of your terminal.

This guide will help you set up and run the Gator CLI. The project is written in Go, and it uses PostgreSQL as the database backend. Please make sure that you have both of these tools installed on your system before proceeding.

Prerequisites

To run Gator, you will need the following installed:

Go (1.17 or higher): You can install Go by following the instructions on the official Go website.

PostgreSQL: Gator requires a PostgreSQL database. You can install PostgreSQL by following the instructions on the official PostgreSQL website.

Make sure that PostgreSQL is running and you have access to create databases.

Setting Up the Config File

Before running Gator, you need to create a configuration file in your home directory. The configuration file should be named .gatorconfig.json and should have the following structure:

{
  "db_url": "postgres://username:password@localhost/dbname?sslmode=disable",
  "current_user_name": ""
}

Replace username, password, and dbname with your PostgreSQL credentials and the name of the database you want to use.

Usage

Create a new user:

gator register <name>

Add a feed:

gator addfeed <url>

Start the aggregator:

gator agg 30s

View the posts:

gator browse [limit]

There are a few other commands you'll need as well:

gator login <name> - Log in as a user that already exists

gator users - List all users

gator feeds - List all feeds

gator follow <url> - Follow a feed that already exists in the database

gator unfollow <url> - Unfollow a feed that already exists in the database