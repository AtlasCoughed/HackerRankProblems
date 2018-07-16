
Cloud Computing
- On Demand
- Broad Network
- Resource Pooling
Rapid Elasticity
Measured Server

Every company is a data company.

Virtual data center.

Raw computer  -> Infrastructure as a service (IAAS).
- Pay as you allocate

App code to libraries to data -> Platform as a service (PaaS)
- Pay as you go.

Zone - Region - Data center

Roundtrip 5 milliseconds
- Make things fault tolerant by spreading to multiple zones

Platform as a Service
- Multiregional = redundant systems

15 Regions (Data centers use 2% of world's energy)
- Billed by the second instead of rounding to nearest minute

Kubernetes - container infrastracture

Hadoop

App Engine -> Platform as a service (use of VMs)


GCP -
open source convertible
-> Not trapped into one vendor

Kubernetes - ability to mix and match various microservices across different cloud providers

Stackdriver - manages and monitor across different cloud

-----

GCP - build test and deploy the cloud
Multilayered Security
- Server/Databoards
- Designed by Google
Hardware Security chip (Titan)
Physical security
- Accesss only available to a small subset of people
Cryptographic communication
- rPc data in transit

Red (Orange) team exercises, simulated exercises
- U2F security, phishing

-Vulnerability reward program

What's new in GCP
Project
- IAM - control for admins
- group related business services
- Giving lease amount privileges, only privileges nesseceary for job

Interacting with GCP
1.) Console - web
2.) Cloud shell/ SDK
3.) Mobile App
4.) Rest based API

Resources -> Projects -> Folders -> Directories -> Org Node
- Policies inherited from parent

Project Ids are always unique
- Names are nicknames, whatever

More generous policies overrides (IMPORTANT)

Identity Access Management
- Who can take actions
- Who, what, what resources.
-- Who = Google Account, GSuit Domain group
-- What = Collection of permissions
-- What Resources = Start/ Stop Permissions

Roles
Primitives
- Owner
- Editor
- Viewee (View Only)
- Billing (W/out change resource abilities)

Pre-defined set of roles, can be applied to folder, organization, etc.
- ie.) Big Table - part project, Big Table- instance

Fine grained permissions
- List
- Delete
- Get
- Set Machine type
- Start
- Stop

Minimum amount of rules necessary for their job.
- Start/ stop

- Only at project, or org level; not folder level

Service Account
- Controls server - server interactions
-- Carry server- server comms
-- authenticate one service to another
-- control privileges used by services

Create Service Account to authenticate your virtual machine to cloud storage
- identified by an email address, project_number, project_id
- use crypto keys instead of passwords
- needs to be managed
- Also a resource
- Different VMs = different permissions for groups

Interacting with GCP
SDK - set of tool to manage
- GCP Shell- main command line interface for GCP
- gsutils
- big query

Restful API
- uses JSON, urls, pass info like web browsers
- console = turn on and off APIs, limit

APIs explorer
- Cloud launcher = quick solution
- Solution marketplace containing pre-packaged ready to deploy solutions

Editable Before deployment
- No additiaonl charge underneath normal usage fees
-- Commercially avail. licenses
-- LAMP - Linux, Apache, mySQL, PHP

Virtual Machine
- Fully fledged OS -editable
- CPU/ memory/type of storage
- Network connection

Virtual Private Cloud
- Connect GCP resources
- Static routes
- Global scope
- Subnets within regions
- Span zones
- Different Resources
-- Expand subnets by IP

VPC - one network
- Can have neighboring subnets, two compute engines, in different zones
- great network layers

-- no upfront costs:
-- VM can be either windows, linux and can import images
-- machine type - very small (free f1 micro) to large
-- custom VMs
-- Can add GPUs for data processing
-- Disks: Standard Disk, Solid State Drive, Local SSD, Persistent Disks

(Startup scripts - Apps)
(Snapshops - used to migrate backups)
(Preemptive VMs - Compute engine, delete this VM when its needed in another region/Cheaper)

Preset Memory, CPUs, etc.
- Scaling out, not scaling up, balancing loads.

VPC capabilities
- Routing Tables - We use them to forward traffic from one instance to another
- Firewall, metadata tags
-- VPC belong to GPC projects
--- Cloud Load Balancing
---- in front of your traffic,
---- HTTP/ TCP,
---- cross region/ subregion
---- moves traffic, if region is down

HTTPS Load balancer
- Cross regional load balancer for web app
- Cloud CDN - Partner program

Secure Socket
- SSL Load balancing
- proxy load balancer
- non HTTPS

TCP
- Global TP proxy
- Particular port
- non SSL

Load balancing Internal (internal IP)
- 8.8.8.8 free by Google
- DNS translates the internet hostnames into addresses
- Cloud DNS - same infrastracture - low latency; high availability.
 -- GCP consoles
 -- API
 -- CDN (edge caching)

Cloud Router - enables dyanmic gateway protocol to access the topography of a VPC with an onsite premise network
-- share route information over VPN
-- enables dynamic VPC use
-- ie.) Add subnet to VPC + on premise network will get routes to be seen

Direct Peering - connect any business network to Google
-- Customer doesn't want to use the public internet
-- Peering = router in same public data center as a google point of presence, exchanging traffic
-- Not covered by SLS

Dedicated Interconnect
-- Physical connection, lower latency, higher availability.
-- Direct connection with on-premises Google, may be cheaper than ISP
-- Great for companies that have data intensive apps.

Carrier Peering
-- higher avail
-- lower latency
-- enterprise grade network servers using server proxies.


Cloud Storage
-- Object file system storage. (Binary immutable Objects)
-- Encrypts data before writing to disk
-- Bytes of data with unique key
-- fully managed, no capacity limit, provision capacity
-- Example: website, data, cluster, large files for download
-- Buckets for objects.
-- Can use versioning on these objects
    -- new > old
    -- lifecycle management, "keep most recent", "delete versions > 365 days"
-- Transfer Data - HTTPS
-- Other GCP services
-- Geographic location, default class for buckets
-- Cloud IAM
  -- Project into Buckets
  -- ACL(s) finer control
  -- Scope (users), permissions
-- Storage - all accessible by API
  -- Region
    -- Less redundant
    -- Cheaper
    -- Specific region
    Uses:
      -- Data for compiling
      -- VMS
      -- Kubernetes Engine
  -- Multiregional
    --  High performance
    -- Broad continuation, redundant
    -- Frequently used websites
    -- Interaction control
    -- Mobile app
  Backups and archival storage
  -- Nearline
    -- Infrenquently stored durable data
    -- Read/ write once a month
  -- Coldline
    -- Low cost
    -- Data archival
    -- Online backup
    -- Disaster recovery
    -- Once a year; min allowed time: 90 days

Big Table
-- noSQL, data analysis
-- Single key look-ups
-- HBase (Sql like queries), Hadoop portability
-- Structure data / flexible schemas,
-- Sparely populatd rows
-- Billions of rows, don't need to reconfigure
-- Persistent hash tables
-- Very low latency
-- Handles upgrades easily, highly scalable
-- Encryption
-- Example: From application database stream to spark storage. batch processes, summarize down
-- Uses: iOT, user analytics, financial documents

Cloud SQL
-- DB Schema 0 consitent
-- Transaction is all or nothing; Bank example
-- mySQL, postGreSQL (beta)
-- Managed service or server in VM compute engine
    -- Read duplicates
-- Replica service during outage
-- On demand/ schedule batch
-- Google secruity
-- Scale vertically with machine type
-- SQL workbench with other apps