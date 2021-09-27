# How to remove the gridline of WPF DataGrid(SfDataGrid) with grouping
## About the sample

This example illustrates how to remove the gridline of [WPF DataGrid](https://www.syncfusion.com/wpf-ui-controls/datagrid) (SfDataGrid) with grouping.

[WPF DataGrid](https://www.syncfusion.com/wpf-ui-controls/datagrid) (SfDataGrid) having gird lines for each row and column. But you can remove the grid lines for default row by write style for BorderThickness of [GridCell](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCell.html) and remove the grid lines for caption row by write style for BorderThickness of [GridCaptionSummaryCell](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCaptionSummaryCell.html) and [GridIndentCell](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridIndentCell.html).

```xml
<Style TargetType="syncfusion:GridCell">
    <Setter Property="BorderThickness" Value="0"/>
</Style>
<Style TargetType="syncfusion:GridIndentCell">
    <Setter Property="BorderThickness" Value="0"/>
    <Setter Property="Template">
        <Setter.Value>
            <ControlTemplate TargetType="{x:Type syncfusion:GridIndentCell}">
            </ControlTemplate>
        </Setter.Value>
    </Setter>
</Style>
<Style TargetType="syncfusion:GridCaptionSummaryCell">
    <Setter Property="Template">
        <Setter.Value>
            <ControlTemplate TargetType="{x:Type syncfusion:GridCaptionSummaryCell}">
                <Border x:Name="PART_GridCaptionSummaryCellBorder"
                    BorderThickness="0"
                    SnapsToDevicePixels="True">
                    <ContentPresenter Margin="{TemplateBinding Padding}"
                                  HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}"
                                  VerticalAlignment="{TemplateBinding VerticalContentAlignment}"
                                  SnapsToDevicePixels="True" />
                </Border>
            </ControlTemplate>
        </Setter.Value>
    </Setter>
</Style>
```

KB article - [How to remove the gridline of WPF DataGrid(SfDataGrid) with grouping](https://www.syncfusion.com/kb/11009/how-to-remove-the-gridline-of-wpf-datagrid-sfdatagrid-with-grouping)

## Requirements to run the demo
Visual Studio 2015 and above versions
