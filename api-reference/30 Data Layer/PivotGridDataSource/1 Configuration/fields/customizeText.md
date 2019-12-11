---
type: function(cellInfo)
---
---
##### shortDescription
Customizes the text displayed in summary cells.

##### param(cellInfo): Object
Information on the current cell.

##### field(cellInfo.value): String | Number | Date
The cell's raw value.

##### field(cellInfo.valueText): String
The [formatted](/api-reference/30%20Data%20Layer/PivotGridDataSource/1%20Configuration/fields/format.md '/Documentation/ApiReference/Data_Layer/PivotGridDataSource/Configuration/fields/#format') value converted to a string.

##### return: String
The text for the cell to display.

---
---
##### jQuery

    <!--JavaScript-->
    $(function() {
        var pivotGridDataSource = new DevExpress.data.PivotGridDataSource({
            // ...
            fields: [{
                // ...
                customizeText: function (cellInfo) {
                    // Your code goes here
                }
            }]
        });

        $("#pivotGridContainer").dxPivotGrid({
            dataSource: pivotGridDataSource
        });
    });
    

##### Angular

    <!--TypeScript-->
    import PivotGridDataSource from "devextreme/ui/pivot_grid/data_source";
    import { DxPivotGridModule } from "devextreme-angular";
    // ...
    export class AppComponent {
        pivotGridDataSource: PivotGridDataSource;
        constructor() {
            this.pivotGridDataSource = new PivotGridDataSource({
                // ...
                fields: [{
                    // ...
                    customizeText: function (cellInfo) {
                        // Your code goes here
                    }
                }]
            });
        }
    }

    @NgModule({
        imports: [
            // ...
            DxPivotGridModule
        ],
        // ...
    })

    <!--HTML-->
    <dx-pivot-grid
        [dataSource]="pivotGridDataSource">
    </dx-pivot-grid>

##### ASP.NET MVC Controls

    <!--Razor C#-->
    @(Html.DevExtreme().PivotGrid()
        .DataSource(ds => ds
            // ...
            .Fields(fields => {
                fields.Add()
                    // ...
                    .CustomizeText("customizeText");
            })
        )
    )

    <script type="text/javascript">
        function customizeText (cellInfo) {
            // Your code goes here
        }
    </script>

---

#include uiwidgets-ref-functioncontext with { 
    value: "field's configuration"
}