# Load More without offset
# Use case
1. A lightning data table with load more feature
2. Link to a field redirecting to details page
3. Data table showing parent data
4. Workaround for offset limit 2000

# Solution 
There are 2 components and a class created to cover the mentioned use cases.
Class LoadMoreWithoutOffset has 2 methods and a wrapper class. 
If your requirement is to show data from parent object along with child details then you can use "getOpportunityDetails" method with wrapper class "DataWrapper".
If you dont need parent data to be shown in lightning data table then you can directly use the method "getOpportunityDetailsWithoutWrapper". No need of wrapper class and the other method in this scenario.

Component "loadMoreWithoutOffset" is created to show the parent data along with child details whereas "loadMoreWithoutOffsetWithoutWrapper" component doesn't show any data from parent object.

# Note
1. If there is null value present in the Order by field then ensure sorting the data accordinly. Preferably NULL at the end.
2. If you dont want scroll bar in your lightning data table and still want LoadMore feature on Button click then use below code snippet for data table and button -
```
<lightning-datatable key-field=id data={dataOpportunity} columns={columns} 
    onrowaction={handleRowAction} hide-checkbox-column>
</lightning-datatable>
<div>
    <lightning-button variant="brand" label="Load More" title="Click to load more records" onclick={handleLoadMore}></lightning-button>
</div>
```
# Author
Pradeep Gayaki
