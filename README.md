Bread Crumbs Component
===

Bread crumds Navigation is also called breadcrumbs.
The bread crumd is the mechanism for navigating from view to view.


### grammar:
+ [Angular](https://angular.io),
+ [Type Script](http://www.typescriptlang.org/),
+ [SCSS](http://sass-lang.com/)

# KscBreadCrumbsComponent

create a ksc-bread-crumbs.component.ts file
```ts
import { Component } from '@angular/core';

@Component({
     selector: 'ksc-bread-crumbs',
     template: `<ul class="bread-crumb-ul">
              <ng-container *ngFor="let item of data">
                <li (click)="item.bindFunc" *ngIf="item.isActive"><a href={{item.href}}>{{item.name}}</a></li>
              </ng-container>
             </ul>`,
   styleUrls: ['./ksc-bread-crumbs.component.scss']
})
```

Write the HTML in ``template`` , and create scss file and write the route in`` styleUrls:[`  `]``

import ``Input``

```ts
import { Component, Input } from '@angular/core';
```


`` @Input() ``: Input decorator and metadata. It corresponds to data of HTML:``*ngFor="let item of data"``

```ts

@Input('data')
  public set data(value: any) {
    this._data = value;
  } 
  
```


 then `` export`` the ``class`` of KscBreadCrumbsComponent to use to others.

```ts
export class KscBreadCrumbsComponent {
  private _data: any;
  constructor() { }
  public get data() {
    return this._data;
  }
  ```
## SCSS
```
 $bread-crumbs-li-font-size : 12px;
 $bread-crumbs-li-parents-color : #282EC9;
 $bread-crumbs-li-corrent-color : #000;

.bread-crumb-ul {
  padding: 12px 0px;
  list-style: none;
  font-size: $bread-crumbs-li-font-size !important;
}

.bread-crumb-ul >li {
  display: inline ;
}

.bread-crumb-ul >li >a {
  text-decoration: underline;
}

.bread-crumb-ul >li:last-child >a {
  color: $bread-crumbs-li-corrent-color;
  text-decoration: none;
}

.bread-crumb-ul >li + li:before {
  padding: 8px;
  color: $bread-crumbs-li-corrent-color;
  content: "\003E";
}
```
You can define a size variable like `` $bread-crumbs-li-font-size : 12px;``,
then you can use the size like 
```
bread-crumb-ul {
  padding: 12px 0px;
  list-style: none;
  font-size: $bread-crumbs-li-font-size !important;
}
```

Finish those you should find your project main component , and quote the mudule.

