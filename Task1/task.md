* The Pod should run in the core namespace. The namespace should be create first.

* The name of the Pod should be inspect

* Use the 1fccncf/redis image with the 3.2 tag,verify the events and fix the issue with the image later

* Expose containerPort 6379


```mermaid
graph LR
A[Square Rect] -- Link text --> B((Circle))
A --> C(Round Rect)
B --> D{Rhombus}
C --> D
