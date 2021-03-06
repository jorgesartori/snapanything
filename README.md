SnapTwitter for App Engine Standard (Java 8)
============================

Automatically delete tweets after a interval of days

See the [Google App Engine standard environment documentation][ae-docs] for more
detailed instructions.

[ae-docs]: https://cloud.google.com/appengine/docs/java/


* [Java 8](http://www.oracle.com/technetwork/java/javase/downloads/index.html)
* [Maven](https://maven.apache.org/download.cgi) (at least 3.5)
* [Gradle](https://gradle.org/gradle-download/) (optional)
* [Google Cloud SDK](https://cloud.google.com/sdk/) (aka gcloud)

## Setup

• Download and initialize the [Cloud SDK](https://cloud.google.com/sdk/)

    gcloud init

* Create an App Engine app within the current Google Cloud Project


    gcloud app create

* Change the **your-project-ID-goes-here** information at `pom.xml` to your Google App Engine Project ID

* Access [https://apps.twitter.com/](https://apps.twitter.com/)

* Create new app

* Manage Keys and Access Tokens

* Create my access token

* Copy Keys, Secrets and Tokens

* Edit the **final variables** at `MyTwitter.java` filling up with your credentials and to personalize behavior   

## Maven
### Running locally

    mvn appengine:run

To use vist: 
* [http://localhost:8080/timeline?rt](http://localhost:8080/timeline?rt) to delete retweeted tweets below average
* [http://localhost:8080/timeline](http://localhost:8080/timeline) to delete recent tweets
* [http://localhost:8080/timeline?ot](http://localhost:8080/timeline?ot) to delete old tweets

### Deploying

    mvn appengine:deploy

Upload your cron
    
    ./appengine-java-sdk/bin/appcfg.sh -A your-app-id -V app-version update_cron [YOUR_APP_DIR]

To use vist:  https://YOUR-PROJECT-ID.appspot.com