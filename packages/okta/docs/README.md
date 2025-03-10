# Okta Integration

The Okta integration collects events from the Okta API, specifically reading from the Okta System Log API.

## Logs

### System

The Okta System Log records system events related to your organization in order to provide an audit trail that can be used to understand platform activity and to diagnose problems. This module is implemented using the httpjson input and is configured to paginate through the logs while honoring any rate-limiting headers sent by Okta.

An example event for `system` looks as following:

```json
{
    "@timestamp": "2020-02-14T20:18:57.718Z",
    "agent": {
        "ephemeral_id": "c8d18964-83d3-4be1-809c-201de8688e6b",
        "hostname": "docker-fleet-agent",
        "id": "62554406-4558-40ed-9cd2-c68d978882ff",
        "name": "docker-fleet-agent",
        "type": "filebeat",
        "version": "7.13.0"
    },
    "client": {
        "geo": {
            "city_name": "Dublin",
            "country_name": "United States",
            "location": {
                "lat": 37.7201,
                "lon": -121.919
            },
            "region_name": "California"
        },
        "ip": "108.255.197.247",
        "user": {
            "full_name": "xxxxxx",
            "id": "00u1abvz4pYqdM8ms4x6"
        }
    },
    "data_stream": {
        "dataset": "okta.system",
        "namespace": "ep",
        "type": "logs"
    },
    "ecs": {
        "version": "1.9.0"
    },
    "elastic_agent": {
        "id": "52c5ef7a-f604-488a-b39c-4ab431eb930e",
        "snapshot": true,
        "version": "7.13.0"
    },
    "event": {
        "action": "user.session.start",
        "category": [
            "authentication",
            "session"
        ],
        "created": "2021-05-31T10:31:04.833Z",
        "dataset": "okta.system",
        "id": "3aeede38-4f67-11ea-abd3-1f5d113f2546",
        "ingested": "2021-05-31T10:31:05.861084700Z",
        "kind": "event",
        "original": "{\"actor\":{\"alternateId\":\"xxxxxx@elastic.co\",\"detailEntry\":null,\"displayName\":\"xxxxxx\",\"id\":\"00u1abvz4pYqdM8ms4x6\",\"type\":\"User\"},\"authenticationContext\":{\"authenticationProvider\":null,\"authenticationStep\":0,\"credentialProvider\":null,\"credentialType\":null,\"externalSessionId\":\"102bZDNFfWaQSyEZQuDgWt-uQ\",\"interface\":null,\"issuer\":null},\"client\":{\"device\":\"Computer\",\"geographicalContext\":{\"city\":\"Dublin\",\"country\":\"United States\",\"geolocation\":{\"lat\":37.7201,\"lon\":-121.919},\"postalCode\":\"94568\",\"state\":\"California\"},\"id\":null,\"ipAddress\":\"108.255.197.247\",\"userAgent\":{\"browser\":\"FIREFOX\",\"os\":\"Mac OS X\",\"rawUserAgent\":\"Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:72.0) Gecko/20100101 Firefox/72.0\"},\"zone\":\"null\"},\"debugContext\":{\"debugData\":{\"deviceFingerprint\":\"541daf91d15bef64a7e08c946fd9a9d0\",\"requestId\":\"XkcAsWb8WjwDP76xh@1v8wAABp0\",\"requestUri\":\"/api/v1/authn\",\"threatSuspected\":\"false\",\"url\":\"/api/v1/authn?\"}},\"displayMessage\":\"User login to Okta\",\"eventType\":\"user.session.start\",\"legacyEventType\":\"core.user_auth.login_success\",\"outcome\":{\"reason\":null,\"result\":\"SUCCESS\"},\"published\":\"2020-02-14T20:18:57.718Z\",\"request\":{\"ipChain\":[{\"geographicalContext\":{\"city\":\"Dublin\",\"country\":\"United States\",\"geolocation\":{\"lat\":37.7201,\"lon\":-121.919},\"postalCode\":\"94568\",\"state\":\"California\"},\"ip\":\"108.255.197.247\",\"source\":null,\"version\":\"V4\"}]},\"securityContext\":{\"asNumber\":null,\"asOrg\":null,\"domain\":null,\"isProxy\":null,\"isp\":null},\"severity\":\"INFO\",\"target\":null,\"transaction\":{\"detail\":{},\"id\":\"XkcAsWb8WjwDP76xh@1v8wAABp0\",\"type\":\"WEB\"},\"uuid\":\"3aeede38-4f67-11ea-abd3-1f5d113f2546\",\"version\":\"0\"}",
        "outcome": "success",
        "type": [
            "start",
            "user"
        ]
    },
    "host": {
        "name": "docker-fleet-agent"
    },
    "input": {
        "type": "httpjson"
    },
    "okta": {
        "actor": {
            "alternate_id": "xxxxxx@elastic.co",
            "display_name": "xxxxxx",
            "id": "00u1abvz4pYqdM8ms4x6",
            "type": "User"
        },
        "authentication_context": {
            "authentication_step": 0,
            "external_session_id": "102bZDNFfWaQSyEZQuDgWt-uQ"
        },
        "client": {
            "device": "Computer",
            "ip": "108.255.197.247",
            "user_agent": {
                "browser": "FIREFOX",
                "os": "Mac OS X",
                "raw_user_agent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:72.0) Gecko/20100101 Firefox/72.0"
            },
            "zone": "null"
        },
        "debug_context": {
            "debug_data": {
                "device_fingerprint": "541daf91d15bef64a7e08c946fd9a9d0",
                "request_id": "XkcAsWb8WjwDP76xh@1v8wAABp0",
                "request_uri": "/api/v1/authn",
                "threat_suspected": "false",
                "url": "/api/v1/authn?"
            }
        },
        "display_message": "User login to Okta",
        "event_type": "user.session.start",
        "outcome": {
            "result": "SUCCESS"
        },
        "transaction": {
            "id": "XkcAsWb8WjwDP76xh@1v8wAABp0",
            "type": "WEB"
        },
        "uuid": "3aeede38-4f67-11ea-abd3-1f5d113f2546"
    },
    "related": {
        "ip": [
            "108.255.197.247"
        ],
        "user": [
            "xxxxxx"
        ]
    },
    "source": {
        "as": {
            "number": 7018,
            "organization": {
                "name": "AT\u0026T Services, Inc."
            }
        },
        "geo": {
            "city_name": "Dublin",
            "continent_name": "North America",
            "country_iso_code": "US",
            "country_name": "United States",
            "location": {
                "lat": 37.7201,
                "lon": -121.919
            },
            "region_iso_code": "US-CA",
            "region_name": "California"
        },
        "ip": "108.255.197.247",
        "user": {
            "full_name": "xxxxxx",
            "id": "00u1abvz4pYqdM8ms4x6"
        }
    },
    "tags": [
        "forwarded",
        "preserve_original_event"
    ],
    "user": {
        "full_name": "xxxxxx"
    },
    "user_agent": {
        "device": {
            "name": "Mac"
        },
        "name": "Firefox",
        "original": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:72.0) Gecko/20100101 Firefox/72.0",
        "os": {
            "full": "Mac OS X 10.15",
            "name": "Mac OS X",
            "version": "10.15"
        },
        "version": "72.0."
    }
}
```

**Exported fields**

| Field | Description | Type |
|---|---|---|
| @timestamp | Event timestamp. | date |
| client.as.number | Unique number allocated to the autonomous system. The autonomous system number (ASN) uniquely identifies each network on the Internet. | long |
| client.as.organization.name | Organization name. | keyword |
| client.domain | Client domain. | keyword |
| client.geo.city_name | City name. | keyword |
| client.geo.country_name | Country name. | keyword |
| client.geo.location | Longitude and latitude. | geo_point |
| client.geo.region_name | Region name. | keyword |
| client.ip | IP address of the client (IPv4 or IPv6). | ip |
| client.user.full_name | User's full name, if available. | keyword |
| client.user.id | Unique identifier of the user. | keyword |
| cloud.account.id | The cloud account or organization id used to identify different entities in a multi-tenant environment. Examples: AWS account id, Google Cloud ORG Id, or other unique identifier. | keyword |
| cloud.availability_zone | Availability zone in which this host is running. | keyword |
| cloud.image.id | Image ID for the cloud instance. | keyword |
| cloud.instance.id | Instance ID of the host machine. | keyword |
| cloud.instance.name | Instance name of the host machine. | keyword |
| cloud.machine.type | Machine type of the host machine. | keyword |
| cloud.project.id | Name of the project in Google Cloud. | keyword |
| cloud.provider | Name of the cloud provider. Example values are aws, azure, gcp, or digitalocean. | keyword |
| cloud.region | Region in which this host is running. | keyword |
| container.id | Unique container id. | keyword |
| container.image.name | Name of the image the container was built on. | keyword |
| container.labels | Image labels. | object |
| container.name | Container name. | keyword |
| data_stream.dataset | Data stream dataset name. | constant_keyword |
| data_stream.namespace | Data stream namespace. | constant_keyword |
| data_stream.type | Data stream type. | constant_keyword |
| destination.as.number | Unique number allocated to the autonomous system. The autonomous system number (ASN) uniquely identifies each network on the Internet. | long |
| destination.as.organization.name | Organization name. | keyword |
| destination.geo.city_name | City name. | keyword |
| destination.geo.continent_name | Name of the continent. | keyword |
| destination.geo.country_iso_code | Country ISO code. | keyword |
| destination.geo.country_name | Country name. | keyword |
| destination.geo.location | Longitude and latitude. | geo_point |
| destination.geo.name | User-defined description of a location, at the level of granularity they care about. Could be the name of their data centers, the floor number, if this describes a local physical entity, city names. Not typically used in automated geolocation. | keyword |
| destination.geo.region_iso_code | Region ISO code. | keyword |
| destination.geo.region_name | Region name. | keyword |
| destination.ip | IP address of the destination (IPv4 or IPv6). | ip |
| ecs.version | ECS version this event conforms to. `ecs.version` is a required field and must exist in all events. When querying across multiple indices -- which may conform to slightly different ECS versions -- this field lets integrations adjust to the schema version of the events. | keyword |
| error.message | Error message. | text |
| event.action | The action captured by the event. This describes the information in the event. It is more specific than `event.category`. Examples are `group-add`, `process-started`, `file-created`. The value is normally defined by the implementer. | keyword |
| event.category | This is one of four ECS Categorization Fields, and indicates the second level in the ECS category hierarchy. `event.category` represents the "big buckets" of ECS categories. For example, filtering on `event.category:process` yields all events relating to process activity. This field is closely related to `event.type`, which is used as a subcategory. This field is an array. This will allow proper categorization of some events that fall in multiple categories. | keyword |
| event.dataset | Event dataset | constant_keyword |
| event.id | Unique ID to describe the event. | keyword |
| event.ingested | Timestamp when an event arrived in the central data store. This is different from `@timestamp`, which is when the event originally occurred.  It's also different from `event.created`, which is meant to capture the first time an agent saw the event. In normal conditions, assuming no tampering, the timestamps should chronologically look like this: `@timestamp` \< `event.created` \< `event.ingested`. | date |
| event.kind | This is one of four ECS Categorization Fields, and indicates the highest level in the ECS category hierarchy. `event.kind` gives high-level information about what type of information the event contains, without being specific to the contents of the event. For example, values of this field distinguish alert events from metric events. The value of this field can be used to inform how these kinds of events should be handled. They may warrant different retention, different access control, it may also help understand whether the data coming in at a regular interval or not. | keyword |
| event.module | Event module | constant_keyword |
| event.original | Raw text message of entire event. Used to demonstrate log integrity or where the full log message (before splitting it up in multiple parts) may be required, e.g. for reindex. This field is not indexed and doc_values are disabled. It cannot be searched, but it can be retrieved from `_source`. If users wish to override this and index this field, please see `Field data types` in the `Elasticsearch Reference`. | keyword |
| event.outcome | This is one of four ECS Categorization Fields, and indicates the lowest level in the ECS category hierarchy. `event.outcome` simply denotes whether the event represents a success or a failure from the perspective of the entity that produced the event. Note that when a single transaction is described in multiple events, each event may populate different values of `event.outcome`, according to their perspective. Also note that in the case of a compound event (a single event that contains multiple logical events), this field should be populated with the value that best captures the overall success or failure from the perspective of the event producer. Further note that not all events will have an associated outcome. For example, this field is generally not populated for metric events, events with `event.type:info`, or any events for which an outcome does not make logical sense. | keyword |
| event.type | This is one of four ECS Categorization Fields, and indicates the third level in the ECS category hierarchy. `event.type` represents a categorization "sub-bucket" that, when used along with the `event.category` field values, enables filtering events down to a level appropriate for single visualization. This field is an array. This will allow proper categorization of some events that fall in multiple event types. | keyword |
| host.architecture | Operating system architecture. | keyword |
| host.containerized | If the host is a container. | boolean |
| host.domain | Name of the domain of which the host is a member. For example, on Windows this could be the host's Active Directory domain or NetBIOS domain name. For Linux this could be the domain of the host's LDAP provider. | keyword |
| host.hostname | Hostname of the host. It normally contains what the `hostname` command returns on the host machine. | keyword |
| host.id | Unique host id. As hostname is not always unique, use values that are meaningful in your environment. Example: The current usage of `beat.name`. | keyword |
| host.ip | Host ip addresses. | ip |
| host.mac | Host mac addresses. | keyword |
| host.name | Name of the host. It can contain what `hostname` returns on Unix systems, the fully qualified domain name, or a name specified by the user. The sender decides which value to use. | keyword |
| host.os.build | OS build information. | keyword |
| host.os.codename | OS codename, if any. | keyword |
| host.os.family | OS family (such as redhat, debian, freebsd, windows). | keyword |
| host.os.kernel | Operating system kernel version as a raw string. | keyword |
| host.os.name | Operating system name, without the version. | keyword |
| host.os.platform | Operating system platform (such centos, ubuntu, windows). | keyword |
| host.os.version | Operating system version as a raw string. | keyword |
| host.type | Type of host. For Cloud providers this can be the machine type like `t2.medium`. If vm, this could be the container, for example, or other information meaningful in your environment. | keyword |
| input.type | Type of Filebeat input. | keyword |
| log.file.path | Path to the log file. | keyword |
| log.flags | Flags for the log file. | keyword |
| log.offset | Offset of the entry in the log file. | long |
| message | For log events the message field contains the log message, optimized for viewing in a log viewer. For structured logs without an original message field, other fields can be concatenated to form a human-readable summary of the event. If multiple messages exist, they can be combined into one message. | text |
| okta.actor.alternate_id | Alternate identifier of the actor. | keyword |
| okta.actor.display_name | Display name of the actor. | keyword |
| okta.actor.id | Identifier of the actor. | keyword |
| okta.actor.type | Type of the actor. | keyword |
| okta.authentication_context.authentication_provider | The information about the authentication provider. Must be one of OKTA_AUTHENTICATION_PROVIDER, ACTIVE_DIRECTORY, LDAP, FEDERATION, SOCIAL, FACTOR_PROVIDER. | keyword |
| okta.authentication_context.authentication_step | The authentication step. | integer |
| okta.authentication_context.credential_provider | The information about credential provider. Must be one of OKTA_CREDENTIAL_PROVIDER, RSA, SYMANTEC, GOOGLE, DUO, YUBIKEY. | keyword |
| okta.authentication_context.credential_type | The information about credential type. Must be one of OTP, SMS, PASSWORD, ASSERTION, IWA, EMAIL, OAUTH2, JWT, CERTIFICATE, PRE_SHARED_SYMMETRIC_KEY, OKTA_CLIENT_SESSION, DEVICE_UDID. | keyword |
| okta.authentication_context.external_session_id | The session identifer of the external session if any. | keyword |
| okta.authentication_context.interface | The interface used. e.g., Outlook, Office365, wsTrust | keyword |
| okta.authentication_context.issuer.id | The identifier of the issuer. | keyword |
| okta.authentication_context.issuer.type | The type of the issuer. | keyword |
| okta.client.device | The information of the client device. | keyword |
| okta.client.id | The identifier of the client. | keyword |
| okta.client.ip | The IP address of the client. | ip |
| okta.client.user_agent.browser | The browser informaton of the client. | keyword |
| okta.client.user_agent.os | The OS informaton. | keyword |
| okta.client.user_agent.raw_user_agent | The raw informaton of the user agent. | keyword |
| okta.client.zone | The zone information of the client. | keyword |
| okta.debug_context.debug_data.device_fingerprint | The fingerprint of the device. | keyword |
| okta.debug_context.debug_data.request_id | The identifier of the request. | keyword |
| okta.debug_context.debug_data.request_uri | The request URI. | keyword |
| okta.debug_context.debug_data.threat_suspected | Threat suspected. | keyword |
| okta.debug_context.debug_data.url | The URL. | keyword |
| okta.display_message | The display message of the LogEvent. | keyword |
| okta.event_type | The type of the LogEvent. | keyword |
| okta.outcome.reason | The reason of the outcome. | keyword |
| okta.outcome.result | The result of the outcome. Must be one of: SUCCESS, FAILURE, SKIPPED, ALLOW, DENY, CHALLENGE, UNKNOWN. | keyword |
| okta.request.ip_chain.geographical_context.city | The city. | keyword |
| okta.request.ip_chain.geographical_context.country | The country. | keyword |
| okta.request.ip_chain.geographical_context.geolocation | Geolocation information. | geo_point |
| okta.request.ip_chain.geographical_context.postal_code | The postal code. | keyword |
| okta.request.ip_chain.geographical_context.state | The state. | keyword |
| okta.request.ip_chain.ip | IP address. | ip |
| okta.request.ip_chain.source | Source information. | keyword |
| okta.request.ip_chain.version | IP version. Must be one of V4, V6. | keyword |
| okta.security_context.as.number | The AS number. | integer |
| okta.security_context.as.organization.name | The organization name. | keyword |
| okta.security_context.domain | The domain name. | keyword |
| okta.security_context.is_proxy | Whether it is a proxy or not. | boolean |
| okta.security_context.isp | The Internet Service Provider. | keyword |
| okta.severity | The severity of the LogEvent. Must be one of DEBUG, INFO, WARN, or ERROR. | keyword |
| okta.target.alternate_id | Alternate identifier of the actor. | keyword |
| okta.target.display_name | Display name of the actor. | keyword |
| okta.target.id | Identifier of the actor. | keyword |
| okta.target.type | Type of the actor. | keyword |
| okta.transaction.id | Identifier of the transaction. | keyword |
| okta.transaction.type | The type of transaction. Must be one of "WEB", "JOB". | keyword |
| okta.uuid | The unique identifier of the Okta LogEvent. | keyword |
| okta.version | The version of the LogEvent. | keyword |
| related.ip | All of the IPs seen on your event. | ip |
| related.user | All the user names or other user identifiers seen on the event. | keyword |
| source.as.number | Unique number allocated to the autonomous system. The autonomous system number (ASN) uniquely identifies each network on the Internet. | long |
| source.as.organization.name | Organization name. | keyword |
| source.domain | Source domain. | keyword |
| source.geo.city_name | City name. | keyword |
| source.geo.continent_name | Name of the continent. | keyword |
| source.geo.country_iso_code | Country ISO code. | keyword |
| source.geo.country_name | Country name. | keyword |
| source.geo.location | Longitude and latitude. | geo_point |
| source.geo.name | User-defined description of a location, at the level of granularity they care about. Could be the name of their data centers, the floor number, if this describes a local physical entity, city names. Not typically used in automated geolocation. | keyword |
| source.geo.region_iso_code | Region ISO code. | keyword |
| source.geo.region_name | Region name. | keyword |
| source.ip | IP address of the source (IPv4 or IPv6). | ip |
| source.user.full_name | User's full name, if available. | keyword |
| source.user.id | Unique identifier of the user. | keyword |
| tags | List of keywords used to tag each event. | keyword |
| user.domain | Name of the directory the user is a member of. For example, an LDAP or Active Directory domain name. | keyword |
| user.email | User email address. | keyword |
| user.full_name | User's full name, if available. | keyword |
| user.id | Unique identifier of the user. | keyword |
| user.name | Short name or login of the user. | keyword |
| user.target.domain | Name of the directory the user is a member of. For example, an LDAP or Active Directory domain name. | keyword |
| user.target.email | User email address. | keyword |
| user.target.full_name | User's full name, if available. | keyword |
| user.target.group.domain | Name of the directory the group is a member of. For example, an LDAP or Active Directory domain name. | keyword |
| user.target.group.id | Unique identifier for the group on the system/platform. | keyword |
| user.target.group.name | Name of the group. | keyword |
| user.target.id | Unique identifier of the user. | keyword |
| user.target.name | Short name or login of the user. | keyword |
| user_agent.device.name | Name of the device. | keyword |
| user_agent.name | Name of the user agent. | keyword |
| user_agent.original | Unparsed user_agent string. | keyword |
| user_agent.os.full | Operating system name, including the version or code name. | keyword |
| user_agent.os.name | Operating system name, without the version. | keyword |
| user_agent.os.version | Operating system version as a raw string. | keyword |
| user_agent.version | Version of the user agent. | keyword |
