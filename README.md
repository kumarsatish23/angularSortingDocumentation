# ngx-sortable-table is an Angular library that provides sorting functionality for tables. It allows you to easily add sorting capabilities to your tables by using a directive.

To use ngx-sortable-table, you need to follow these steps:

1. Install the ngx-sortable-table library by running the following command in your Angular project directory:

   ```
   npm install ngx-sortable-table
   ```

2. Import the SortableTableModule into your Angular module:

   ```typescript
   import { SortableTableModule } from 'ngx-sortable-table';

   @NgModule({
     imports: [
       SortableTableModule
     ]
   })
   export class YourModule { }
   ```

3. In your HTML template, add the `sortable` directive to the table header cells that you want to make sortable. You can specify the property name to be used for sorting using the `sortable` attribute:

   ```html
   <table>
     <thead>
       <tr>
         <th sortable="name">Name</th>
         <th sortable="age">Age</th>
         <!-- Other table headers -->
       </tr>
     </thead>
     <tbody>
       <!-- Table rows -->
     </tbody>
   </table>
   ```

4. In your component, define the data array that populates the table:

   ```typescript
   import { Component } from '@angular/core';

   @Component({
     selector: 'app-your-component',
     templateUrl: './your-component.component.html'
   })
   export class YourComponent {
     data = [
       { name: 'John', age: 30 },
       { name: 'Jane', age: 25 },
       // Other data items
     ];
   }
   ```

5. Finally, you can access the sorted data in your component by listening to the `sortChanged` event emitted by the sortable table:

   ```html
   <table (sortChanged)="onSortChanged($event)">
     <!-- Table content -->
   </table>
   ```

   ```typescript
   export class YourComponent {
     onSortChanged(sortedData: any[]) {
       // Access the sorted data here
     }
   }
   ```

With ngx-sortable-table, the table headers with the `sortable` directive will have sorting functionality enabled. Clicking on a sortable header will trigger the sorting of the table data based on the specified property. The sorted data can be accessed in your component for further processing or display.
