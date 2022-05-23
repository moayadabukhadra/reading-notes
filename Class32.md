# DRF Permissions

- permissions determine whether a request should be granted or denied access.

- Permission checks are always run at the very start of the view, before any other code is allowed to proceed. Permission checks will typically use the authentication information in the request.user and request.auth properties to determine if the incoming request should be permitted.

## How permissions are determined

- Permissions in REST framework are always defined as a list of permission classes.

- Before running the main body of the view each permission in the list is checked. If any permission check fails, an exceptions.PermissionDenied or exceptions.NotAuthenticated exception will be raised, and the main body of the view will not run.

## Object level permissions

- REST framework permissions also support object-level permissioning. Object level permissions are used to determine if a user should be allowed to act on a particular object, which will typically be a model instance.

## Setting the permission policy

- The default permission policy may be set globally, using the DEFAULT_PERMISSION_CLASSES setting. For example.

```
REST_FRAMEWORK = {
    'DEFAULT_PERMISSION_CLASSES': [
        'rest_framework.permissions.IsAuthenticated',
    ]
}
```

- If not specified, this setting defaults to allowing unrestricted access:

```
'DEFAULT_PERMISSION_CLASSES': [
   'rest_framework.permissions.AllowAny',
]
```

- You can also set the authentication policy on a per-view, or per-viewset basis, using the APIView class-based views.

```
from rest_framework.permissions import IsAuthenticated
from rest_framework.response import Response
from rest_framework.views import APIView

class ExampleView(APIView):
    permission_classes = [IsAuthenticated]

    def get(self, request, format=None):
        content = {
            'status': 'request was permitted'
        }
        return Response(content)
```

# API Reference

- The AllowAny permission class will allow unrestricted access, regardless of if the request was authenticated or unauthenticated.

This permission is not strictly required, since you can achieve the same result by using an empty list or tuple for the permissions setting, but you may find it useful to specify this class because it makes the intention explicit.

## IsAuthenticated

- The IsAuthenticated permission class will deny permission to any unauthenticated user, and allow permission otherwise.

This permission is suitable if you want your API to only be accessible to registered users.

## IsAdminUser

- The IsAdminUser permission class will deny permission to any user, unless user.is_staff is True in which case permission will be allowed.

This permission is suitable if you want your API to only be accessible to a subset of trusted administrators.

- You can read more [here](https://www.django-rest-framework.org/api-guide/permissions/)