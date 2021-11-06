# measure-region-latency
This package provides way to measure rough latency on each region of cloud services from your env.

## Supporting service
### AWS
 - It uses root of regional dynamodb API endpoint. It provides health status.
 - It is not exact latency, but it's good way to know roughly how long it takes to the region from your env.

## Pre-requirement
It depends on [Locust](https://github.com/locustio/locust). Please install locust in your environment by following [official doc](http://docs.locust.io/en/stable/installation.html)..

## Getting started

1. Go to folder of cloud service name. (Just AWS now
2. Execute the following command
```
locust --headless --users 5 --spawn-rate 1 -t 1m -H dummy
```

### Sample result

From WA state of US..
```
Response time percentiles (approximated)
 Type     Name                               50%    66%    75%    80%    90%    95%    98%    99%  99.9% 99.99%   100% # reqs
--------|-----------------------------|---------|------|------|------|------|------|------|------|------|------|------|------|
 GET      af-south-1 region                 1300   1300   1300   1300   1300   1500   1500   1500   1500   1500   1500     20
 GET      ap-east-1 region                   730    750    760    760    790    810    810    810    810    810    810     20
 GET      ap-northeast-1 region              530    560    570    570    630    670    670    670    670    670    670     20
 GET      ap-northeast-2 region              630    640    670    690    710    720    720    720    720    720    720     20
 GET      ap-northeast-3 region              540    550    570    580    600    670    670    670    670    670    670     20
 GET      ap-south-1 region                 1000   1100   1100   1100   1200   1400   1400   1400   1400   1400   1400     20
 GET      ap-southeast-1 region              830    850    880    910    950   1000   1000   1000   1000   1000   1000     20
 GET      ap-southeast-2 region              700    710    720    720    730    740    740    740    740    740    740     20
 GET      ca-central-1 region                440    460    470    500    560    560    560    560    560    560    560     20
 GET      eu-central-1 region                710    730    740    750    760    770    770    770    770    770    770     20
 GET      eu-north-1 region                  810    850    860    870    900   1100   1100   1100   1100   1100   1100     17
 GET      eu-south-1 region                  770    800    810    810    820    850    850    850    850    850    850     20
 GET      eu-west-1 region                   700    720    740    740    770   1200   1200   1200   1200   1200   1200     20
 GET      eu-west-2 region                   700    720    720    730    800   1700   1700   1700   1700   1700   1700     20
 GET      eu-west-3 region                   690    700    710    720    740    760    760    760    760    760    760     20
 GET      me-south-1 region                  990   1000   1000   1000   1100   1100   1100   1100   1100   1100   1100     16
 GET      sa-east-1 region                   840    850    920    930    940    970    970    970    970    970    970     15
 GET      us-east-1 region                   390    410    410    410    430    530    530    530    530    530    530     20
 GET      us-east-2 region                   400    410    430    430    550    620    620    620    620    620    620     20
 GET      us-gov-east-1 region               390    390    420    430    520    530    530    530    530    530    530     15
 GET      us-gov-west-1 region               140    140    170    180    200    220    220    220    220    220    220     15
 GET      us-west-1 region                   200    210    210    220    230    270    270    270    270    270    270     20
 GET      us-west-2 region                   150    200    200    200    270    410    410    410    410    410    410     20
--------|-----------------------------|---------|------|------|------|------|------|------|------|------|------|------|------|
 None     Aggregated                         680    740    800    830   1000   1200   1300   1300   1700   1700   1700    438
```

## License

Open source licensed under the MIT license (see LICENSE file for details).
