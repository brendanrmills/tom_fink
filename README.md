# Fink Alert Broker Module for the TOM Toolkit

This repository hosts the Fink Alert Broker Module for the TOM Toolkit. Fink is a broker currently connected to ZTF. More information on Fink at https://fink-broker.org/.

As of version 0.1, the module simply uses the Fink REST API to retrieve alerts. Note that the Fink databases are updated once a day with the previous night alert data (hence you do not get live alerts for the moment).

## How to use the Fink module inside your TOM

First, install the module using pip

```
pip install tom-fink
```

then you need to declare it in your running TOM instance. To do so just add `tom_fink.fink.FinkBroker` to the `TOM_ALERT_CLASSES` in your TOM's `settings.py`:

```
TOM_ALERT_CLASSES = [
  'tom_alerts.brokers.alerce.ALeRCEBroker',
  ...,
  'tom_fink.fink.FinkBroker'
]
```

and finally relaunch your TOM:

```
./manage.py runserver
```

## Todo list

- [ ] Add a test suite (preferably running on GitHub Actions)
- [ ] Add a linter (preferably running on GitHub Actions)
- [ ] Update the Query Form with all API features
- [ ] Enable querying livestreams using the Fink Kafka client
