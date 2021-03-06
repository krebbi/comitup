% comitup-conf(5)
%
% April 2018

# NAME

comitup.conf -- Comitup configuration file format

## DESCRIPTION

The _comitup.conf_ file configures the wifi management service comitup(8).
It is located in the _/etc/_ directory.

## PARAMETERS

  * _base_name_:
    By default, comitup will create a hotspot named **comitup-&lt;nnnn&gt;**, and publish
    avahi-daemon(8) host entries for **comitup-&lt;nnnn&gt;** and **comitup**. Setting this
    entry will change the **comitup** string with one of the users choosing.

  * _web_service_:
    This defines a user web service to be controlled by **comitup**. This service will be
    disabled in the **HOTSPOT** state in preference of the comitup web service, and will be
    enabled in the **CONNECTED** state. This should be the name of the systemd web service,
    such as _apache2.service_ or _nginx.service_. This defaults to a null string,
    meaning no service is controlled.

  * _enable_appliance_mode_:
    By default, comitup will use multiple wifi interfaces, if available, to connect to the
    local hotspot and to the internet simultaneously. Setting this to something other than
    "true" will limit comitup to the first wifi interface.

  * _external_callback_:

    The path to an external script that is called on comitup state changes. It will include
    a single argument, either 'HOTSPOT', 'CONNECTING', or 'CONNECTED'. The script will run
    as the owning user and group.

## COPYRIGHT

Comitup is Copyright (C) 2016-2017 David Steele &lt;steele@debian.org&gt;

## SEE ALSO

comitup(8), comitup-cli(1), comitup-web(8)

