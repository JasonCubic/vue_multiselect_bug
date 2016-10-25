# to recreate the vue-multiselect bug

1. Start the project as normal and goto the webpack-dev-server page
2. Select an option from the multiselect
3. open the multiselect and use the scrollbar

In chrome it behaves as expected.  In IE the list seems to collapse down to only the one item that was selected.
