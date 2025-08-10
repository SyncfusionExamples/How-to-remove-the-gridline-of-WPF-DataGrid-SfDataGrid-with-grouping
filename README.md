# How to remove the gridline of WPF DataGrid with grouping?

In [WPF DataGrid](https://www.syncfusion.com/wpf-ui-controls/datagrid) (SfDataGrid) having gird lines for each row and column. But we can remove the grid lines for default row by write style for BorderThickness of [GridCell](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCell.html) and remove the grid lines for caption row by write style for BorderThickness of [GridCaptionSummaryCell](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridCaptionSummaryCell.html) and [GridIndentCell](https://help.syncfusion.com/cr/cref_files/wpf/Syncfusion.SfGrid.WPF~Syncfusion.UI.Xaml.Grid.GridIndentCell.html).

```xml
<Style TargetType="syncfusion:GridCell">
    <Setter Property="BorderThickness" Value="0"/>
</Style>

<Style TargetType="syncfusion:GridIndentCell">
    <Setter Property="BorderThickness" Value="0"/>
    <Setter Property="Template">
        <Setter.Value>
            <ControlTemplate TargetType="{x:Type syncfusion:GridIndentCell}">
                <!-- Add template content if needed in future -->
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
Take a moment to peruse the [WPF DataGrid - Style and Templates](https://help.syncfusion.com/wpf/datagrid/styles-and-templates) documentation, where you can find about the styles with code examples.

## Requirements to run the demo
Visual Studio 2015 and above versions
