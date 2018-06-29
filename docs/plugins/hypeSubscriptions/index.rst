hypeSubscriptions
=================

API for implementing paid subscriptions

 * Agnostic API that can be extended with any payment provider
 * Implement site subscriptions and optionally restrict access to paying subscribers only
 * API to implement entity/group specific subscriptions
 * API to restrict access to posts and downloads


Events
~~~~~~

To implement custom logic when the subscription is created, listen to ``create, subscription`` event.

To implement custom logic when the subscription cancelled, listing to ``cancel, subscription``. Note that the sbuscription can be cancelled at period end, so check ``current_period_end`` metadata, before terminating access to features.
