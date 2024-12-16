import truecallerjs, { SearchData, Format } from "truecallerjs";

async function performTruecallerSearch(): Promise<void> {
  const searchData: SearchData = {
    number: "6291131249",
    countryCode: "IN",
    installationId: "a1k07--Vgdfyvv_rftf5uuudhuhnkljyvvtfftjuhbuijbhug",
  };

  try {
    const response: Format = await truecallerjs.search(searchData);
    console.log(response.json());

    // Additional response methods:
    // console.log(response.xml());
    // console.log(response.yaml());
    // console.log(response.text());

    // Example of available data from the response:
    console.log(response.getName()); // "Sumith Emmadi"
    console.log(response.getAlternateName()); // "sumith"
    console.log(response.getAddresses()); // {....}
    console.log(response.getEmailId()); // example@domain.com
    console.log(response.getCountryDetails()); // {...}
  } catch (error) {
    console.error("Error occurred:", error);
  }
}

performTruecallerSearch();
