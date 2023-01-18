# Creating a custom dashboard

[Insert introduction here]

#### Creating an angular component
To use a custom dashboard you must first create a component to hold both
the functionality and user interface.<br/>
First create a package under 'src/app/' and then create an angular component such as the example below
```typescript
import { Component, OnInit } from '@angular/core';

@Component({
    selector: 'app-dashboard',
    templateUrl: './dashboard.component.html',
    styleUrls: []
})
export class DashboardComponent implements OnInit {

    constructor() { }

    ngOnInit(): void {
    }

}
```
Create the html file that will serve your user interface. Note that the name of the file must be the same 
as in the templateUrl property in the example above.
```html
<div style="display: grid;justify-items: center">
  <h1>Hello world!</h1>
</div>
```
#### Routing
Valtimo already provides an off the shelf dashboard which must first be overridden in order for your 
custom dashboard to be used.<br/>
To achieve that you can import and declare the route as in the example below.
```typescript
import {DashboardComponent} from './custom-components/dashboard/dashboard.component';

const routes: Routes = [{
  path: '',
  component: DashboardComponent,
  data: {title: 'My Custom Dashboard', roles: ['ROLE_USER']},
  canActivate: [AuthGuardService]
}];
```
The path variable in the example above is the key for overriding components. As it stands
the default Valtimo dashboard exists under the root path so the value must be an empty string.<br/>
The title property can be defined, and it will be shown in the header of the page, and the roles
defines the which role can access the page (more on roles [here](#))

#### Declaring the component module
In order for your component to be used by the application you must import and declare it in 'app.module.ts'

```typescript
@NgModule({
  declarations: [
    AppComponent,
    DashboardComponent
  ]
})
```
