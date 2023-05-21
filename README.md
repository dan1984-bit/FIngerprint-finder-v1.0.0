# Fingerprint finder

Fingerprint finder is a simple console application and java library for fingerprint matching.

## Requirements
To build application from source code you need Apache Maven 3 installed and to run application you need Java version 11+.

## Building

In the root package run next command. Builded jar file can be found with path `target/fingerprint-finder-1.0.0.jar`

```bash
mvn clean package
```
## Usage of application
```java
#run application
java -jar fingerprint-finder-1.0.0.jar

Welcome to Fingerprint Finder! 
Type "help" to see all available commands

#save .tif fingerprint in buffer
save "C:/somepath/somefingerprint.tif"
Saved

#save multiple .tif fingerprints in buffer from directory
saveAll "C:/somepath/fingerprints"
Saved

#returns integer index if match is found and warning if not
find "C:/somepath/fingerprint_to_find.tif"
Match found in record with index 11

```

## Usage as library

```bash
import com.zolotoverchy.daniel.finder.FingerPrintFinder;

# create new stateful object
FingerPrintFinder finder = new FingerPrintFinder();

# save .tif fingerprint in buffer 
finder.save("C:/somepath/somefingerprint.tif")

# save multiple .tif fingerprints in buffer from directory 
finder.saveAll("C:/somepath/fingerprints")

# returns integer index if match is found and throws Exception if not
finder.find("C:/somepath/fingerprint_to_find.tif")

# returns current size of buffer
finder.getBufferSize();
```
