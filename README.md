# ToDoApp

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 1.7.0.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `-prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).

CASE 
      WHEN start_time BETWEEN CAST('08:00:00' AS time) AND CAST('18:00:00' AS time) 
      AND end_time BETWEEN CAST('08:00:00' AS time) AND CAST('18:00:00' AS time) THEN DATEDIFF(MINUTE, start_time, end_time)
      WHEN start_time BETWEEN CAST('08:00:00' AS time) AND CAST('18:00:00' AS time) 
      AND end_time NOT BETWEEN CAST('08:00:00' AS time) AND CAST('18:00:00' AS time) THEN DATEDIFF(MINUTE, start_time, CAST('18:00:00' AS timestamp))
      WHEN start_time NOT BETWEEN CAST('08:00:00' AS time) AND CAST('18:00:00' AS time) 
      AND end_time BETWEEN CAST('08:00:00' AS time) AND CAST('18:00:00' AS time) THEN DATEDIFF(MINUTE, CAST('08:00:00' AS timestamp), end_time)
      ELSE 0
    END AS day_minutes,
    DATEDIFF(MINUTE, start_time, end_time) - 
    CASE 
      WHEN start_time BETWEEN CAST('08:00:00' AS time) AND CAST('18:00:00' AS time) 
      AND end_time BETWEEN CAST('08:00:00' AS time) AND CAST('18:00:00' AS time) THEN DATEDIFF(MINUTE, start_time, end_time)
      WHEN start_time BETWEEN CAST('08:00:00' AS time) AND CAST('18:00:00' AS time) 
      AND end_time NOT BETWEEN CAST('08:00:00' AS time) AND CAST('18:00:00' AS time) THEN DATEDIFF(MINUTE, start_time, CAST('18:00:00' AS timestamp))
      WHEN start_time NOT BETWEEN CAST('08:00:00' AS time) AND CAST('18:00:00' AS time) 
      AND end_time BETWEEN CAST('08:00:00' AS time) AND CAST('18:00:00' AS time) THEN DATEDIFF(MINUTE, CAST('08:00:00' AS timestamp), end_time)
      ELSE 0
    END AS night_minutes
