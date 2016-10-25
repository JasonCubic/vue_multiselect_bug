<template>

<!-- http://monterail.github.io/vue-multiselect/ -->
<multiselect
  :options="salesCampaigns"
  :show-labels="false"
  @update="updateSelectedCampaign"
  label="CampaignProgramName"
  placeholder="Select Sales Campaign">
  <span slot="noResult">No sales campaigns found.  Consider changing the search query.</span>
</multiselect>

<p>&nbsp;</p>
<p>&nbsp;</p>
<p>&nbsp;</p>
<div v-if="selectedSalesCampaign && selectedSalesCampaign.SCId">
  <h3>selectedSalesCampaign:</h3>
  <p>SCId: {{selectedSalesCampaign.SCId}}</p>
  <p>CampaignProgramName: {{selectedSalesCampaign.CampaignProgramName}}</p>
  <p>CampaignProgramNumber: {{selectedSalesCampaign.CampaignProgramNumber}}</p>
  <p>CampaignRequestor: {{selectedSalesCampaign.CampaignRequestor}}</p>
  <p>AnnounceDate: {{selectedSalesCampaign.AnnounceDate}}</p>
  <p>EndDate: {{selectedSalesCampaign.EndDate}}</p>
  <p>Brand: {{selectedSalesCampaign.Brand}}</p>
  <p>Status: {{selectedSalesCampaign.Status}}</p>
  <p>SalesProgramType: {{selectedSalesCampaign.SalesProgramType}}</p>
</div>

</template>

<script>
import Multiselect from 'vue-multiselect';

function updateSelectedCampaign(newSelectedCampaign) {
  console.log('newSelectedCampaign: ', newSelectedCampaign);
  this.selectedSalesCampaign = newSelectedCampaign;
}

export default {
  components: {
    Multiselect,
  },
  methods: {
    updateSelectedCampaign,
  },
  data() {
    return {
      selectedSalesCampaign: {},
      salesCampaigns: [{
        "SCId": 1,
        "CampaignProgramName": "2016 Vocational Demo Program",
        "CampaignProgramNumber": "DOC-0181",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2013-08-08T00:00:00",
        "EndDate": "2014-08-28T00:00:00",
        "Brand": null,
        "Status": "Feasibility in Progress",
        "SalesProgramType": null
      }, {
        "SCId": 2,
        "CampaignProgramName": "Flying M Winter/Spring Financing Event",
        "CampaignProgramNumber": "DOC-0185",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2014-07-15T00:00:00",
        "EndDate": "2014-12-31T00:00:00",
        "Brand": " Flying M",
        "Status": "Feasibility in Progress",
        "SalesProgramType": " pacific NW; GT Quote"
      }, {
        "SCId": 3,
        "CampaignProgramName": "Test Campaign 3",
        "CampaignProgramNumber": "SC-003",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-03-01T00:00:00",
        "EndDate": "2016-08-31T00:00:00",
        "Brand": " Flying M",
        "Status": "Feasibility in Progress",
        "SalesProgramType": " pacific NW; GT Quote"
      }, {
        "SCId": 4,
        "CampaignProgramName": "Another Test",
        "CampaignProgramNumber": "SC-004",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-10-04T00:00:00",
        "EndDate": "2016-10-05T00:00:00",
        "Brand": null,
        "Status": "Rejected",
        "SalesProgramType": null
      }, {
        "SCId": 5,
        "CampaignProgramName": "Test1",
        "CampaignProgramNumber": "SC001",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-08-17T00:00:00",
        "EndDate": "2016-08-31T00:00:00",
        "Brand": " Flying M",
        "Status": "Pending",
        "SalesProgramType": " pacific NW; GT Quote"
      }, {
        "SCId": 6,
        "CampaignProgramName": "Test2",
        "CampaignProgramNumber": "Sc002",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-08-10T00:00:00",
        "EndDate": "2016-08-31T00:00:00",
        "Brand": " Flying M",
        "Status": "Feasibility in Progress",
        "SalesProgramType": " Business Quote"
      }, {
        "SCId": 7,
        "CampaignProgramName": "Test2",
        "CampaignProgramNumber": "Sc002",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-08-10T00:00:00",
        "EndDate": "2016-08-30T00:00:00",
        "Brand": " Flying M; Flying M Export Models",
        "Status": "Feasibility in Progress",
        "SalesProgramType": " Business Quote; pacific NW; Other; GT Quote"
      }, {
        "SCId": 8,
        "CampaignProgramName": "Test5",
        "CampaignProgramNumber": "Sc 005",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-08-09T00:00:00",
        "EndDate": "2016-08-30T00:00:00",
        "Brand": " Flying M",
        "Status": "Feasibility in Progress",
        "SalesProgramType": " pacific NW; GT Quote"
      }, {
        "SCId": 9,
        "CampaignProgramName": "Test6",
        "CampaignProgramNumber": "SC006",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-08-01T00:00:00",
        "EndDate": "2016-08-24T00:00:00",
        "Brand": " Flying M; Western Star",
        "Status": "Change Requested",
        "SalesProgramType": " pacific NW; StarQuote"
      }, {
        "SCId": 10,
        "CampaignProgramName": "test 7 more",
        "CampaignProgramNumber": "SC007",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-08-17T00:00:00",
        "EndDate": "2016-09-03T00:00:00",
        "Brand": " Flying M",
        "Status": "Change Requested",
        "SalesProgramType": " Business Quote; pacific NW; GT Quote"
      }, {
        "SCId": 11,
        "CampaignProgramName": "test7",
        "CampaignProgramNumber": "test7",
        "CampaignRequestor": "Joe Requestor",
        "AnnounceDate": "2016-08-26T00:00:00",
        "EndDate": "2016-08-26T00:00:00",
        "Brand": " Flying M",
        "Status": "Change Requested",
        "SalesProgramType": " Business Quote; pacific NW; GT Quote"
      }, {
        "SCId": 12,
        "CampaignProgramName": "test7",
        "CampaignProgramNumber": "test7",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-08-26T00:00:00",
        "EndDate": "2016-08-26T00:00:00",
        "Brand": " Western Star",
        "Status": "Feasibility in Progress",
        "SalesProgramType": " StarQuote"
      }, {
        "SCId": 13,
        "CampaignProgramName": "Test8",
        "CampaignProgramNumber": "SC008",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-08-02T00:00:00",
        "EndDate": "2016-08-31T00:00:00",
        "Brand": " Flying M",
        "Status": "Change Requested",
        "SalesProgramType": " Business Quote; pacific NW; GT Quote"
      }, {
        "SCId": 14,
        "CampaignProgramName": "Test9",
        "CampaignProgramNumber": "Sc009",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2013-08-08T00:00:00",
        "EndDate": "2014-10-15T00:00:00",
        "Brand": " Flying M",
        "Status": "Feasibility in Progress",
        "SalesProgramType": " pacific NW; GT Quote"
      }, {
        "SCId": 15,
        "CampaignProgramName": "Test10",
        "CampaignProgramNumber": "Sc010",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-08-17T00:00:00",
        "EndDate": "2017-02-17T00:00:00",
        "Brand": " Western Star",
        "Status": "Feasibility in Progress",
        "SalesProgramType": " StarQuote"
      }, {
        "SCId": 16,
        "CampaignProgramName": "Test10",
        "CampaignProgramNumber": "Sc010",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2013-08-08T00:00:00",
        "EndDate": "2014-10-15T00:00:00",
        "Brand": " Flying M",
        "Status": "Feasibility in Progress",
        "SalesProgramType": " Business Quote; pacific NW; GT Quote"
      }, {
        "SCId": 17,
        "CampaignProgramName": "Test10",
        "CampaignProgramNumber": "Sc010",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-08-17T00:00:00",
        "EndDate": "2016-08-31T00:00:00",
        "Brand": " Flying M",
        "Status": "Feasibility in Progress",
        "SalesProgramType": " pacific NW; GT Quote"
      }, {
        "SCId": 18,
        "CampaignProgramName": "Test10",
        "CampaignProgramNumber": "Sc010",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-08-17T00:00:00",
        "EndDate": "2016-08-31T00:00:00",
        "Brand": " Flying M",
        "Status": "Feasibility in Progress",
        "SalesProgramType": " pacific NW"
      }, {
        "SCId": 19,
        "CampaignProgramName": "test11",
        "CampaignProgramNumber": "test11",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2013-08-08T00:00:00",
        "EndDate": "2014-10-15T00:00:00",
        "Brand": " Western Star",
        "Status": "Draft",
        "SalesProgramType": " StarQuote"
      }, {
        "SCId": 20,
        "CampaignProgramName": "Test12",
        "CampaignProgramNumber": "Test12",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-08-08T00:00:00",
        "EndDate": "2016-08-24T00:00:00",
        "Brand": " Flying M Export Models",
        "Status": "Draft",
        "SalesProgramType": " Other"
      }, {
        "SCId": 21,
        "CampaignProgramName": "test 13",
        "CampaignProgramNumber": "test 13",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-08-02T00:00:00",
        "EndDate": "2016-08-25T00:00:00",
        "Brand": " Flying M",
        "Status": "Feasibility in Progress",
        "SalesProgramType": " pacific NW"
      }, {
        "SCId": 22,
        "CampaignProgramName": "test 14",
        "CampaignProgramNumber": "test 14",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-08-02T00:00:00",
        "EndDate": "2016-08-26T00:00:00",
        "Brand": " Flying M",
        "Status": "Draft",
        "SalesProgramType": " pacific NW"
      }, {
        "SCId": 23,
        "CampaignProgramName": "test 15",
        "CampaignProgramNumber": "test 15",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-08-01T00:00:00",
        "EndDate": "2016-08-31T00:00:00",
        "Brand": " Flying M",
        "Status": "Published",
        "SalesProgramType": " pacific NW"
      }, {
        "SCId": 24,
        "CampaignProgramName": "test 16",
        "CampaignProgramNumber": "test 16",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-08-03T00:00:00",
        "EndDate": "2016-08-05T00:00:00",
        "Brand": " Flying M",
        "Status": "Draft",
        "SalesProgramType": " GT Quote"
      }, {
        "SCId": 25,
        "CampaignProgramName": "test 17",
        "CampaignProgramNumber": "test 17",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-08-16T00:00:00",
        "EndDate": "2016-08-18T00:00:00",
        "Brand": null,
        "Status": "Draft",
        "SalesProgramType": null
      }, {
        "SCId": 26,
        "CampaignProgramName": "test 18",
        "CampaignProgramNumber": "test 18",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-08-04T00:00:00",
        "EndDate": "2016-09-01T00:00:00",
        "Brand": null,
        "Status": "Draft",
        "SalesProgramType": null
      }, {
        "SCId": 27,
        "CampaignProgramName": "test 19",
        "CampaignProgramNumber": "test 19",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-08-03T00:00:00",
        "EndDate": "2016-08-18T00:00:00",
        "Brand": null,
        "Status": "Feasibility in Progress",
        "SalesProgramType": null
      }, {
        "SCId": 28,
        "CampaignProgramName": "test 20",
        "CampaignProgramNumber": "test 20",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-08-10T00:00:00",
        "EndDate": "2016-08-18T00:00:00",
        "Brand": null,
        "Status": "Draft",
        "SalesProgramType": null
      }, {
        "SCId": 29,
        "CampaignProgramName": "test 21",
        "CampaignProgramNumber": "test 21",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-08-19T00:00:00",
        "EndDate": "2016-08-25T00:00:00",
        "Brand": " Flying M",
        "Status": "Draft",
        "SalesProgramType": " GT Quote"
      }, {
        "SCId": 30,
        "CampaignProgramName": "Test Create",
        "CampaignProgramNumber": "TST-CR01",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-09-01T00:00:00",
        "EndDate": "2017-03-31T00:00:00",
        "Brand": " Flying M",
        "Status": "Draft",
        "SalesProgramType": " pacific NW"
      }, {
        "SCId": 31,
        "CampaignProgramName": "Test 19",
        "CampaignProgramNumber": "PGM-19",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-09-07T00:00:00",
        "EndDate": "2016-09-06T00:00:00",
        "Brand": " Flying M",
        "Status": "Draft",
        "SalesProgramType": " Business Quote; pacific NW; GT Quote"
      }, {
        "SCId": 32,
        "CampaignProgramName": "Test 20",
        "CampaignProgramNumber": "PGM-20",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-09-21T00:00:00",
        "EndDate": "2016-09-14T00:00:00",
        "Brand": " Flying M",
        "Status": "Draft",
        "SalesProgramType": " pacific NW; GT Quote"
      }, {
        "SCId": 33,
        "CampaignProgramName": "Test23",
        "CampaignProgramNumber": "PGM-23",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-09-27T00:00:00",
        "EndDate": "2016-12-30T00:00:00",
        "Brand": " Flying M",
        "Status": "Draft",
        "SalesProgramType": " GT Quote"
      }, {
        "SCId": 34,
        "CampaignProgramName": "Test 23",
        "CampaignProgramNumber": "PGM-23",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-09-14T00:00:00",
        "EndDate": "2016-12-30T00:00:00",
        "Brand": " Flying M",
        "Status": "Change Requested",
        "SalesProgramType": " Business Quote"
      }, {
        "SCId": 35,
        "CampaignProgramName": "Test Date Defaults",
        "CampaignProgramNumber": "4352",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-09-27T00:00:00",
        "EndDate": "2016-12-31T00:00:00",
        "Brand": " Flying M",
        "Status": "Draft",
        "SalesProgramType": " GT Quote"
      }, {
        "SCId": 36,
        "CampaignProgramName": "Test Default Dates",
        "CampaignProgramNumber": "TST-D01",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-10-10T00:00:00",
        "EndDate": "2016-12-31T00:00:00",
        "Brand": " Flying M",
        "Status": "Draft",
        "SalesProgramType": " GT Quote"
      }, {
        "SCId": 37,
        "CampaignProgramName": "test pgm",
        "CampaignProgramNumber": "PGM-37",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-10-04T00:00:00",
        "EndDate": "2016-11-10T00:00:00",
        "Brand": " Western Star",
        "Status": "Change Requested",
        "SalesProgramType": " StarQuote"
      }, {
        "SCId": 38,
        "CampaignProgramName": "Test Tracking Gen",
        "CampaignProgramNumber": "PGM-38",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-10-04T00:00:00",
        "EndDate": "2017-04-14T00:00:00",
        "Brand": " Western Star",
        "Status": "Draft",
        "SalesProgramType": " StarQuote"
      }, {
        "SCId": 39,
        "CampaignProgramName": "Test Program End Dates",
        "CampaignProgramNumber": "PGM-39",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-10-04T00:00:00",
        "EndDate": "2017-01-15T00:00:00",
        "Brand": " Western Star",
        "Status": "Draft",
        "SalesProgramType": " StarQuote"
      }, {
        "SCId": 40,
        "CampaignProgramName": "GPE1",
        "CampaignProgramNumber": "PGM-40",
        "CampaignRequestor": "Fred Requestor",
        "AnnounceDate": "2016-11-01T00:00:00",
        "EndDate": "2017-02-28T00:00:00",
        "Brand": " Western Star",
        "Status": "Change Requested",
        "SalesProgramType": " StarQuote"
      }, {
        "SCId": 41,
        "CampaignProgramName": "Test for Create",
        "CampaignProgramNumber": "PGM-41",
        "CampaignRequestor": "Fred Requestor",
        "AnnounceDate": "2016-11-01T00:00:00",
        "EndDate": "2017-11-16T00:00:00",
        "Brand": " Flying M",
        "Status": "Draft",
        "SalesProgramType": " GT Quote"
      }, {
        "SCId": 42,
        "CampaignProgramName": "Testing ",
        "CampaignProgramNumber": "PGM-42",
        "CampaignRequestor": "Fred from accounting",
        "AnnounceDate": "2016-10-18T00:00:00",
        "EndDate": "2017-01-31T00:00:00",
        "Brand": " Flying M",
        "Status": "Draft",
        "SalesProgramType": " GT Quote"
      }, {
        "SCId": 43,
        "CampaignProgramName": "Fire Sale",
        "CampaignProgramNumber": "PGM-43",
        "CampaignRequestor": "Joe Requestor",
        "AnnounceDate": "2016-10-18T00:00:00",
        "EndDate": "2016-10-28T00:00:00",
        "Brand": " Flying M",
        "Status": "Draft",
        "SalesProgramType": " pacific NW"
      }, {
        "SCId": 44,
        "CampaignProgramName": "Quater 4 Pgm",
        "CampaignProgramNumber": "PGM-44",
        "CampaignRequestor": "Fred Requestor",
        "AnnounceDate": "2016-10-18T00:00:00",
        "EndDate": "2016-10-28T00:00:00",
        "Brand": " Flying M Export Models",
        "Status": "Draft",
        "SalesProgramType": " Other"
      }, {
        "SCId": 45,
        "CampaignProgramName": "test pgm",
        "CampaignProgramNumber": "PGM-45",
        "CampaignRequestor": "Fred Requestor",
        "AnnounceDate": "2016-10-18T00:00:00",
        "EndDate": "2016-10-28T00:00:00",
        "Brand": " Flying M",
        "Status": "Published",
        "SalesProgramType": " GT Quote"
      }, {
        "SCId": 46,
        "CampaignProgramName": "pgp test",
        "CampaignProgramNumber": "PGM-46",
        "CampaignRequestor": "Fred Requestor",
        "AnnounceDate": "2016-10-18T00:00:00",
        "EndDate": "2016-11-04T00:00:00",
        "Brand": " Flying M",
        "Status": "Draft",
        "SalesProgramType": " GT Quote"
      }, {
        "SCId": 47,
        "CampaignProgramName": "New Templeton",
        "CampaignProgramNumber": "PGM-47",
        "CampaignRequestor": "Joe Requestor",
        "AnnounceDate": "2016-11-01T00:00:00",
        "EndDate": "2017-04-30T00:00:00",
        "Brand": " Flying M",
        "Status": "Feasibility in Progress",
        "SalesProgramType": " pacific NW"
      }, {
        "SCId": 48,
        "CampaignProgramName": "test 24",
        "CampaignProgramNumber": "PGM-48",
        "CampaignRequestor": "Fred Requestor",
        "AnnounceDate": "2016-10-18T00:00:00",
        "EndDate": "2016-10-19T00:00:00",
        "Brand": " Flying M Export Models",
        "Status": "Draft",
        "SalesProgramType": " Other"
      }, {
        "SCId": 49,
        "CampaignProgramName": "test 26",
        "CampaignProgramNumber": "PGM-49",
        "CampaignRequestor": "Fred Requestor",
        "AnnounceDate": "2016-10-18T00:00:00",
        "EndDate": "2016-10-19T00:00:00",
        "Brand": " Flying M Export Models",
        "Status": "Draft",
        "SalesProgramType": " Other"
      }],
    };
  },
};
</script>

<style>
  body {
    background-color: #E8E8E8;
  }
</style>
