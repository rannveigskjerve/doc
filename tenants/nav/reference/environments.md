# Available environments

NAIS provides environments both on-prem and running in Google Cloud Platform (GCP).

This is a overview over the different environments and their capabilities and available domains.

We also enumerate the external IPs used by the environments, so that you can provide them to services that require IP allow-listing.

## Google Cloud Platform (GCP)

!!! info

    The environments in GCP is the recommended place to run your workloads. 
    Compared to the on-prem environments, the GCP environments are more stable and have more and better features.

### dev-gcp

#### Domains

| domain | accessible from | description |
| :--- | :--- | :--- |
| ekstern.dev.nav.no | internet | development ingress for applications exposed to internet. URLs containing `/metrics`, `/actuator` or `/internal` are blocked. |
| intern.dev.nav.no  | [naisdevice](../explanation/naisdevice.md) and NAV internal networks | development ingress for non-public/internet-facing applications |

#### External IPs

- 35.228.4.248
- 34.88.219.93
- 35.228.165.176

### prod-gcp

#### Domains

| domain | accessible from | description |
| :--- | :--- | :--- |
| nav.no | internet | subdomains are manually configured, contact at \#tech-sikkerhet. Ingresses on `nav.no/*` are automatically available. URLs containing `/metrics`, `/actuator` or `/internal` are blocked |
| intern.nav.no | [naisdevice](../explanation/naisdevice.md) | used by non-public/internet-facing applications \(previously called adeo.no\). |

#### External IPs

- 35.228.235.189
- 35.228.12.134
- 35.228.189.194


## On-prem

!!! warning

    This is a legacy environment, and is not recommended for new workloads.

### dev-fss

#### Domains

| domain              | accessible from                   | description                                                                                                                                                                       |
| :------------------ | :-------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| intern.dev.nav.no   | [naisdevice](../explanation/naisdevice.md) | development ingress for internal applications. Also available in dev-gcp, use this to ease migration                                                                              |
| dev-fss-pub.nais.io | GCP                               | See [How do I reach an application found on-premises from my application in GCP?](migrating-to-gcp.md#how-do-i-reach-an-application-found-on-premises-from-my-application-in-gcp) |

### prod-fss

#### Domains

| domain               | accessible from                   | description                                                                                                                                                                       |
| :------------------- | :-------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| intern.nav.no        | [naisdevice](../explanation/naisdevice.md) | ingress for internal applications (supersedes nais.adeo.no). Also available in prod-gcp, use this to ease migration. Requires [JITA](./naisdevice/jita.md) to `onprem-k8s-prod`      |
| prod-fss-pub.nais.io | GCP                               | See [How do I reach an application found on-premises from my application in GCP?](../explanation/migrating-to-gcp.md#how-do-i-reach-an-application-found-on-premises-from-my-application-in-gcp) |
