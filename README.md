# closePopup
close div or popup on click outside

Add below function in parent Div.
 **showPopup(1,$event)**
 
 **Example**
   <a class="ui-kit-menu__item w-tab mr-10" data-tab="breadcrumbs" (click)="showPopup(1,$event)"
      [ngClass]="tAuto == true ? 'active':''">
  

Add below function in child div (Popup) 
  (click)="$event.stopPropagation()"
    
  **Example**
  <p-autoComplete (click)="$event.stopPropagation()" id="senderAutocomplete" #autoCompleteObject *ngIf="tAuto">  ....../... </p-autoComplete 
    
    
    
   Add in TS file
    
     @HostListener('document:click', ['$event']) onDocumentClick(event) {
     this.showPopup(2, event);
     event.stopPropagation()
     }
    
    
    showPopup(id, event) {
    if (id == 1) {
      this.tAuto = true;
      event.stopPropagation()
    } else {
      this.tAuto = false;
    }
  }
  
    
  
