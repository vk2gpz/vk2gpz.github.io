make build.gradle with :

```
plugins {
    id "java"
    id "maven-publish"
}

group "com.vk2gpz.java.libralies"
version "1.0.0"

sourceCompatibility = JavaVersion.VERSION_1_8
targetCompatibility = JavaVersion.VERSION_1_8

/************* maven publishiung ***************/
publishing {
    repositories {
        maven {
            /*
            This will publish the libraries to the specified folder
            as maven repository.
            Then make sure to push maven-private repository to Github.
             */
            url "file:${rootDir}/repo"
        }
    }

    publications {
// Spigot
        jarFileSpigot_1_7_10(MavenPublication) {
            groupId 'org.spigotmc'
            artifactId 'spigot'
            version '1.7.10'
            artifact file('lib/spigot-1.7.10-1.8-R0.1-1656.jar')
        }
        
        // .... other .jar files
    }
}
```
