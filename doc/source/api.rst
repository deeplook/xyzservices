.. _reference:


API reference
=============

Python API
----------

.. currentmodule:: xyzservices

.. autoclass:: TileProvider
   :members: build_url, requires_token,

.. autoclass:: Bunch
   :exclude-members: clear, copy, fromkeys, get, items, keys, pop, popitem, setdefault, update, values

Providers JSON
--------------

After the installation, you will find the JSON used as a database of providers in
``share/xyzservices/providers.json`` if you want to use it outside of a Python ecosystem.
The JSON is compressed and structured along the following model example:

.. code-block:: json

   {
      "single_provider_name": {
         "url": "https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png",
         "max_zoom": 19,
         "attribution": "(C) OpenStreetMap contributors",
         "name": "OpenStreetMap.Mapnik"
      },
      "provider_bunch_name": {
         "first_provider_name": {
               "url": "https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png",
               "max_zoom": 19,
               "attribution": "(C) OpenStreetMap contributors",
               "name": "OpenStreetMap.Mapnik"
         },
         "second_provider_name": {
               "url": "https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png?access-token={accessToken}",
               "max_zoom": 19,
               "attribution": "(C) OpenStreetMap contributors",
               "name": "OpenStreetMap.Mapnik",
               "accessToken": "<insert your access token here>"
         }
      }
   }
