# Single-tenant Data for AI / ML and apps
Eliminates the dependency on Big Tech, all the data is stored both on your devices and in your personal cloud. Full replication and mobility between data centers, to avoid the risk of de-platforming (being blocked by a provider). Zero surveilance, full privacy as only you can look at your own data, and full control over your own data, as you need no permissions from anyone to use your data.


## Cost-effective data storage  
    * Storage for source datasets, like fitness and health, finance, car, home, etc.
    * Intermediate storage, e.g. enhanced or synthetic datasets, or temporary datasets
    * Storage for trained AI models
    * Storage and streaming access to common data sets (e.g. list of medical conditions, medicines, etc.). Streaming avoids the need to copy large datasets.

## Less time and effort administrating 
    * Common semantics for data
    * Data explorer that uses semantics to show the data on screens
    * Search engine that uses semantics to index data for google-like searches

## Commercial model, incentives and payments
    * Dataset providers
    * AI models providers
    * Semantics providers
    * Data centers as providers of underlying compute resources

## AI / ML (upcoming)
    * Pre-configued environment for training and inference in different systems (MXNET, Tensorflow, etc.)
    * Federated coordination
    * Decentralized federation, improving on Federated model by removing central coordination for a final AI model
    * Integration with leading ML tools
    * Oprimization path to the efficient inference-only models

## Database
    * Multi-master leaderless database (tolerant to network interruptions)
    * Multi-device support, including cloud, desktop and mobile devices
    * Offline support - works even without an internet connection
    * Auto-indexing
    * Structured and semi-structured data
    * Multiple interfaces
      * DynamoDB compaible API
      * LevelDB (LelevUP) API
      * (upcoming) ANSI SQL Use SQL for all your data, structured or semi-structured, including support for joins across data types, databases and external tables.
      * (upcoming) JDBC, ODBC
    
## Data pipelines
    * Bulk data consumption
    * Real-time streaming: 
        * fast sequential loads
        * sparse data download, fast-forward, rewind
        * Accelerated streaming via bittorrent-like bandwidth sharing
    * Sort-merge multiple streams
    * Event-based data consumption. Another term used is Change Data Capture (CDC), which mostly applies to capturing changes in external data sources. Event based processing is used for processing Big Data, which are not possible or costly to load or copy,  to gain instant insights into the data, to update aggregations (counts, sums, etc.), to update AI models. It is also very useful for instant UI updates without requiring a person to do a page refresh.
    * User-defined functions.  Scripting to process data with in-engine JavaScript functions to perform custom calculations.
        * Scale scripting via multiple parallel micro-services
    * Time-travel. Easily access historical data or roll back without manual backups

## Collaboration and data sharing
    * Share live datasets with your partners with a single source-of-truth proofs
    * (Upcoming) Use like Google Drive, Dropbox, but without Google or anyone else in the middle 
    * (Upcoming) Google Docs alternative 
    * (Upcoming) Share parts of the datasets, permisssioned for different data consumers

## Data governanace 
    * Data protection
        * immutability and data versioning
        * data anonymization 
        * data minimization 
    * Guarantee for data validity 
        * verified data origin (doctor credentials, device signature)
    * Schema
    * Standardized storage formats 
    * Support for structured and semi-structured data types, including IoT data

## Data marketplace for training models (upcoming)
    * Data marketplace (catalogs, and commercial consumption of data)
    * Schema marketplace (tokenized NFT)
    * Data accounting for billing

## Data environment for Voice Assistant
    - Messaging and data store for [CloudPal Voice](https://github.com/tradle/cloudpal/blob/main/voiceAssistant.md)
    - Store for Voice Apps executables


