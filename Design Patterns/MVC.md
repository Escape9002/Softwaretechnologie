[mdn web docs](https://developer.mozilla.org/de/docs/Glossary/MVC)

This is less of a pattern and more of a Architecture for your software.

Often you can split your software into these fields:
- Model
- View
- Controller

The model simulates what ever behaviour you want.
- particle simulation
- updates subscribers if something nice happened ([[Observer]])

The View takes the output of the model and makes it pretty
- generate a video or image
- delegates user input to the Controller
- Subscribers to model updates (It is the [[Observer]])

The Controller sets the parameters for the model (often an input coming from view) and controls what you can view in the View
- settings like 
	- Video/Image generation
	- Number of particles
	- Gravity not-so-constant

```
      +-----------+         +------------+
User--|   View    |<--------|   Model    |
      +-----------+         +------------+
          |  /|\                /|\  |
          |   |                 |   |
     (User Action) (Model notifies) (View queries)
          |   |                 |   |
         \|/  |                 |   |
      +-----------+             |
      | Controller|-------------+
      +-----------+    (Controller updates Model)
```

> Der **Controller redet niemals direkt mit der View**, um sie zu aktualisieren. Die View aktualisiert sich immer selbst als Reaktion auf eine Änderung im Model.