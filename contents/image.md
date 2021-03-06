### group Images

Images allow you to create series of servers with predefined configuration.
For instance, you can prepare to scale your serving capacity with a front-end image for an Apache server.

#### Images [/images]

##### Create a new image [POST]

Create a new image

The response is an object that has a key called `image`. This key contain a standard `image` object.

+ Attributes
    + organization: `000a115d-2852-4b0a-9ce8-47f1134ba95a` (required, string) - Organization unique identifier
    + name: `my_image` (required, string) - The image name
    + arch: `arm` (required, string) - The architecture type
    + root_volume: `f0361e7b-cbe4-4882-a999-945192b7171b` (required, string) - The root volume unique identifier

+ Request (application/json)

    + Body

            {
                "organization": "000a115d-2852-4b0a-9ce8-47f1134ba95a",
                "arch": "arm",
                "name": "my_image",
                "root_volume": "f0361e7b-cbe4-4882-a999-945192b7171b"
            }

+ Response 201 (application/json)

        {
          "image": {
            "arch": "arm",
            "creation_date": "2014-05-22T12:56:56.984011+00:00",
            "extra_volumes": "[]",
            "from_image": null,
            "from_server": null,
            "id": "98bf3ac2-a1f5-471d-8c8f-1b706ab57ef0",
            "marketplace_key": null,
            "modification_date": "2014-05-22T12:56:56.984011+00:00",
            "name": "my_image",
            "organization": "000a115d-2852-4b0a-9ce8-47f1134ba95a",
            "public": false,
            "root_volume": {
              "id": "f0361e7b-cbe4-4882-a999-945192b7171b",
              "name": "vol-0-1"
            }
          }
        }

##### List all images [GET]

List all images associate with your account

The response is an object that has a key called `images`. This key contain an array of image objects each of which contain the standard `images` attributes.

+ Response 200 (application/json)

        {
          "images": [
            {
              "arch": "arm",
              "creation_date": "2014-05-22T12:56:56.984011+00:00",
              "extra_volumes": "[]",
              "from_image": null,
              "from_server": null,
              "id": "98bf3ac2-a1f5-471d-8c8f-1b706ab57ef0",
              "marketplace_key": null,
              "modification_date": "2014-05-22T12:56:56.984011+00:00",
              "name": "my_image",
              "organization": "000a115d-2852-4b0a-9ce8-47f1134ba95a",
              "public": false,
              "root_volume": {
                "id": "f0361e7b-cbe4-4882-a999-945192b7171b",
                "name": "vol-0-1"
              }
            },
            {
              "arch": "arm",
              "creation_date": "2014-05-22T12:57:22.514299+00:00",
              "extra_volumes": "[]",
              "from_image": null,
              "from_server": null,
              "id": "1f73d975-35fc-4365-9ead-8dab7e54152f",
              "marketplace_key": null,
              "modification_date": "2014-05-22T12:57:22.514299+00:00",
              "name": "my_image_1",
              "organization": "000a115d-2852-4b0a-9ce8-47f1134ba95a",
              "public": false,
              "root_volume": {
                "id": "f0361e7b-cbe4-4882-a999-945192b7171b",
                "name": "vol-0-2"
              }
            }
          ]
        }

#### Operation on a single image [/images/{image_id}]

+ Parameters
    + image_id: `98bf3ac2-a1f5-471d-8c8f-1b706ab57ef0`(required, string) - Image unique identifier

##### Retrieves an image [GET]

List an individual image

The response is an object that has a key called `image`. This key contain a standard `image` object.

+ Response 200 (application/json)

        {
          "image": {
            "arch": "arm",
            "creation_date": "2014-05-22T12:56:56.984011+00:00",
            "extra_volumes": "[]",
            "from_image": null,
            "from_server": null,
            "id": "98bf3ac2-a1f5-471d-8c8f-1b706ab57ef0",
            "marketplace_key": null,
            "modification_date": "2014-05-22T12:56:56.984011+00:00",
            "name": "my_image",
            "organization": "000a115d-2852-4b0a-9ce8-47f1134ba95a",
            "public": false,
            "root_volume": {
              "id": "f0361e7b-cbe4-4882-a999-945192b7171b",
              "name": "vol-0-1"
            }
          }
        }

##### Update an image [PUT]

Update details about a image

The response is an object that has a key called `image`. This key contain a standard `image` object.

+ Request (application/json)

    + Body

            {
                "arch": "arm", 
                "creation_date": "2014-05-22T12:57:22.514299+00:00", 
                "extra_volumes": "[]", 
                "from_image": null, 
                "from_server": null, 
                "id": "1f73d975-35fc-4365-9ead-8dab7e54152f", 
                "marketplace_key": null, 
                "modification_date": "2014-05-22T12:58:42.511040+00:00", 
                "name": "my_image_old", 
                "organization": "000a115d-2852-4b0a-9ce8-47f1134ba95a", 
                "public": false, 
                "root_volume": {
                  "id": "f0361e7b-cbe4-4882-a999-945192b7171b", 
                  "name": "vol-0-1"
                }
            }


+ Response 200 (application/json)

        {
          "image": {
            "arch": "arm",
            "creation_date": "2014-05-22T12:56:56.984011+00:00",
            "extra_volumes": "[]",
            "from_image": null,
            "from_server": null,
            "id": "98bf3ac2-a1f5-471d-8c8f-1b706ab57ef0",
            "marketplace_key": null,
            "modification_date": "2014-05-22T13:00:15.462764+00:00",
            "name": "my_image_old",
            "organization": "000a115d-2852-4b0a-9ce8-47f1134ba95a",
            "public": false,
            "root_volume": {
              "id": "f0361e7b-cbe4-4882-a999-945192b7171b",
              "name": "TOTO"
            }
          }
        }


##### Delete an image [DELETE]

Delete an image

The response code is a 204, which means that the action was successful with no returned body data.

+ Response 204

