<h1 id="optimizely">optimizely</h1>


<h2 id="optimizely.optimizely.Optimizely">Optimizely</h2>

```python
Optimizely(self, datafile, event_dispatcher=None, logger=None, error_handler=None, skip_json_validation=False, user_profile_service=None)
```
Class encapsulating all SDK functionality.
<h3 id="optimizely.optimizely.Optimizely.activate">activate</h3>

```python
Optimizely.activate(self, experiment_key, user_id, attributes=None)
```
Buckets visitor and sends impression event to Optimizely.

Args:
  experiment_key: Experiment which needs to be activated.
  user_id: ID for user.
  attributes: Dict representing user attributes and values which need to be recorded.

Returns:
  Variation key representing the variation the user will be bucketed in.
  None if user is not in experiment or if experiment is not Running.

<h3 id="optimizely.optimizely.Optimizely.track">track</h3>

```python
Optimizely.track(self, event_key, user_id, attributes=None, event_tags=None)
```
Send conversion event to Optimizely.

Args:
  event_key: Event key representing the event which needs to be recorded.
  user_id: ID for user.
  attributes: Dict representing visitor attributes and values which need to be recorded.
  event_tags: Dict representing metadata associated with the event.

<h3 id="optimizely.optimizely.Optimizely.get_variation">get_variation</h3>

```python
Optimizely.get_variation(self, experiment_key, user_id, attributes=None)
```
Gets variation where user will be bucketed.

Args:
  experiment_key: Experiment for which user variation needs to be determined.
  user_id: ID for user.
  attributes: Dict representing user attributes.

Returns:
  Variation key representing the variation the user will be bucketed in.
  None if user is not in experiment or if experiment is not Running.

<h3 id="optimizely.optimizely.Optimizely.is_feature_enabled">is_feature_enabled</h3>

```python
Optimizely.is_feature_enabled(self, feature_key, user_id, attributes=None)
```
Returns true if the feature is enabled for the given user.

Args:
  feature_key: The key of the feature for which we are determining if it is enabled or not for the given user.
  user_id: ID for user.
  attributes: Dict representing user attributes.

Returns:
  True if the feature is enabled for the user. False otherwise.

<h3 id="optimizely.optimizely.Optimizely.get_enabled_features">get_enabled_features</h3>

```python
Optimizely.get_enabled_features(self, user_id, attributes=None)
```
Returns the list of features that are enabled for the user.

Args:
  user_id: ID for user.
  attributes: Dict representing user attributes.

Returns:
  A list of the keys of the features that are enabled for the user.

<h3 id="optimizely.optimizely.Optimizely.get_feature_variable_boolean">get_feature_variable_boolean</h3>

```python
Optimizely.get_feature_variable_boolean(self, feature_key, variable_key, user_id, attributes=None)
```
Returns value for a certain boolean variable attached to a feature flag.

Args:
  feature_key: Key of the feature whose variable's value is being accessed.
  variable_key: Key of the variable whose value is to be accessed.
  user_id: ID for user.
  attributes: Dict representing user attributes.

Returns:
  Boolean value of the variable. None if:
  - Feature key is invalid.
  - Variable key is invalid.
  - Mismatch with type of variable.

<h3 id="optimizely.optimizely.Optimizely.get_feature_variable_double">get_feature_variable_double</h3>

```python
Optimizely.get_feature_variable_double(self, feature_key, variable_key, user_id, attributes=None)
```
Returns value for a certain double variable attached to a feature flag.

Args:
  feature_key: Key of the feature whose variable's value is being accessed.
  variable_key: Key of the variable whose value is to be accessed.
  user_id: ID for user.
  attributes: Dict representing user attributes.

Returns:
  Double value of the variable. None if:
  - Feature key is invalid.
  - Variable key is invalid.
  - Mismatch with type of variable.

<h3 id="optimizely.optimizely.Optimizely.get_feature_variable_integer">get_feature_variable_integer</h3>

```python
Optimizely.get_feature_variable_integer(self, feature_key, variable_key, user_id, attributes=None)
```
Returns value for a certain integer variable attached to a feature flag.

Args:
  feature_key: Key of the feature whose variable's value is being accessed.
  variable_key: Key of the variable whose value is to be accessed.
  user_id: ID for user.
  attributes: Dict representing user attributes.

Returns:
  Integer value of the variable. None if:
  - Feature key is invalid.
  - Variable key is invalid.
  - Mismatch with type of variable.

<h3 id="optimizely.optimizely.Optimizely.get_feature_variable_string">get_feature_variable_string</h3>

```python
Optimizely.get_feature_variable_string(self, feature_key, variable_key, user_id, attributes=None)
```
Returns value for a certain string variable attached to a feature.

Args:
  feature_key: Key of the feature whose variable's value is being accessed.
  variable_key: Key of the variable whose value is to be accessed.
  user_id: ID for user.
  attributes: Dict representing user attributes.

Returns:
  String value of the variable. None if:
  - Feature key is invalid.
  - Variable key is invalid.
  - Mismatch with type of variable.

<h3 id="optimizely.optimizely.Optimizely.set_forced_variation">set_forced_variation</h3>

```python
Optimizely.set_forced_variation(self, experiment_key, user_id, variation_key)
```
Force a user into a variation for a given experiment.

Args:
 experiment_key: A string key identifying the experiment.
 user_id: The user ID.
 variation_key: A string variation key that specifies the variation which the user.
 will be forced into. If null, then clear the existing experiment-to-variation mapping.

Returns:
  A boolean value that indicates if the set completed successfully.

<h3 id="optimizely.optimizely.Optimizely.get_forced_variation">get_forced_variation</h3>

```python
Optimizely.get_forced_variation(self, experiment_key, user_id)
```
Gets the forced variation for a given user and experiment.

Args:
  experiment_key: A string key identifying the experiment.
  user_id: The user ID.

Returns:
  The forced variation key. None if no forced variation key.

<h2 id="optimizely.notification_center">optimizely.notification_center</h2>


<h3 id="optimizely.notification_center.NotificationCenter">NotificationCenter</h3>

```python
NotificationCenter(self, logger)
```
Class encapsulating Broadcast Notifications. The enums.NotifcationTypes includes predefined notifications.
<h4 id="optimizely.notification_center.NotificationCenter.add_notification_listener">add_notification_listener</h4>

```python
NotificationCenter.add_notification_listener(self, notification_type, notification_callback)
```
Add a notification callback to the notification center.

Args:
  notification_type: A string representing the notification type from .helpers.enums.NotificationTypes
  notification_callback: closure of function to call when event is triggered.

Returns:
  Integer notification id used to remove the notification or -1 if the notification has already been added.

<h4 id="optimizely.notification_center.NotificationCenter.remove_notification_listener">remove_notification_listener</h4>

```python
NotificationCenter.remove_notification_listener(self, notification_id)
```
Remove a previously added notification callback.

Args:
  notification_id: The numeric id passed back from add_notification_listener

Returns:
  The function returns boolean true if found and removed, false otherwise.

<h4 id="optimizely.notification_center.NotificationCenter.clear_all_notifications">clear_all_notifications</h4>

```python
NotificationCenter.clear_all_notifications(self)
```
Remove all notifications
<h4 id="optimizely.notification_center.NotificationCenter.clear_notifications">clear_notifications</h4>

```python
NotificationCenter.clear_notifications(self, notification_type)
```
Remove notifications for a certain notification type

Args:
  notification_type: key to the list of notifications .helpers.enums.NotificationTypes

<h4 id="optimizely.notification_center.NotificationCenter.send_notifications">send_notifications</h4>

```python
NotificationCenter.send_notifications(self, notification_type, *args)
```
Fires off the notification for the specific event.  Uses var args to pass in a
arbitrary list of parameter according to which notification type was fired.

Args:
notification_type: Type of notification to fire (String from .helpers.enums.NotificationTypes)
args: variable list of arguments to the callback.

<h2 id="optimizely.helpers.enums.NotificationTypes">NotificationTypes</h2>

```python
NotificationTypes(self)
```
NotificationTypes for the notification_center.NotificationCenter
format is NOTIFICATION TYPE: list of parameters to callback.

ACTIVATE notification listener has the following parameters:
Experiment experiment, str user_id, dict attributes (can be None), Variation variation, Event event
TRACK notification listener has the following parameters:
str event_key, str user_id, dict attributes (can be None), event_tags (can be None), Event event

<h2 id="optimizely.event_dispatcher">optimizely.event_dispatcher</h2>


<h3 id="optimizely.event_dispatcher.EventDispatcher">EventDispatcher</h3>

```python
EventDispatcher(self)
```

<h4 id="optimizely.event_dispatcher.EventDispatcher.dispatch_event">dispatch_event</h4>

```python
EventDispatcher.dispatch_event(event)
```
Dispatch the event being represented by the Event object.

Args:
  event: Object holding information about the request to be dispatched to the Optimizely backend.

<h2 id="optimizely.error_handler">optimizely.error_handler</h2>


<h3 id="optimizely.error_handler.BaseErrorHandler">BaseErrorHandler</h3>

```python
BaseErrorHandler(self)
```
Class encapsulating exception handling functionality.
Override with your own exception handler providing handle_error method.
<h3 id="optimizely.error_handler.NoOpErrorHandler">NoOpErrorHandler</h3>

```python
NoOpErrorHandler(self)
```
Class providing handle_error method which suppresses the error.
<h3 id="optimizely.error_handler.RaiseExceptionErrorHandler">RaiseExceptionErrorHandler</h3>

```python
RaiseExceptionErrorHandler(self)
```
Class providing handle_error method which raises provided exception.
<h2 id="optimizely.exceptions">optimizely.exceptions</h2>


<h3 id="optimizely.exceptions.InvalidAttributeException">InvalidAttributeException</h3>

```python
InvalidAttributeException(self)
```
Raised when provided attribute is invalid.
<h3 id="optimizely.exceptions.InvalidAudienceException">InvalidAudienceException</h3>

```python
InvalidAudienceException(self)
```
Raised when provided audience is invalid.
<h3 id="optimizely.exceptions.InvalidEventTagException">InvalidEventTagException</h3>

```python
InvalidEventTagException(self)
```
Raised when provided event tag is invalid.
<h3 id="optimizely.exceptions.InvalidExperimentException">InvalidExperimentException</h3>

```python
InvalidExperimentException(self)
```
Raised when provided experiment key is invalid.
<h3 id="optimizely.exceptions.InvalidEventException">InvalidEventException</h3>

```python
InvalidEventException(self)
```
Raised when provided event key is invalid.
<h3 id="optimizely.exceptions.InvalidGroupException">InvalidGroupException</h3>

```python
InvalidGroupException(self)
```
Raised when provided group ID is invalid.
<h3 id="optimizely.exceptions.InvalidInputException">InvalidInputException</h3>

```python
InvalidInputException(self)
```
Raised when provided datafile, event dispatcher, logger or error handler is invalid.
<h3 id="optimizely.exceptions.InvalidVariationException">InvalidVariationException</h3>

```python
InvalidVariationException(self)
```
Raised when provided variation is invalid.
<h2 id="optimizely.logger">optimizely.logger</h2>


<h2 id="optimizely.logger.BaseLogger">BaseLogger</h2>

```python
BaseLogger(self)
```
Class encapsulating logging functionality. Override with your own logger providing log method.
<h2 id="optimizely.logger.SimpleLogger">SimpleLogger</h2>

```python
SimpleLogger(self, min_level=20)
```
Class providing log method which logs to stdout.
<h2 id="optimizely.logger.NoOpLogger">NoOpLogger</h2>

```python
NoOpLogger(self)
```
Class providing log method which logs nothing.
<h2 id="optimizely.user_profile">optimizely.user_profile</h2>


<h2 id="optimizely.user_profile.UserProfileService">UserProfileService</h2>

```python
UserProfileService(self)
```
Class encapsulating user profile service functionality.
Override with your own implementation for storing and retrieving the user profile.
<h3 id="optimizely.user_profile.UserProfileService.lookup">lookup</h3>

```python
UserProfileService.lookup(self, user_id)
```
Fetch the user profile dict corresponding to the user ID.

Args:
  user_id: ID for user whose profile needs to be retrieved.

Returns:
  Dict representing the user's profile.

<h3 id="optimizely.user_profile.UserProfileService.save">save</h3>

```python
UserProfileService.save(self, user_profile)
```
Save the user profile dict sent to this method.

Args:
  user_profile: Dict representing the user's profile.

