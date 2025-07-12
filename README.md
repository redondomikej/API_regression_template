after we get the api collection we must check them manually the payload and the reponse , to verify if they working or not by doing this we can know what are the api that is not working and we can coordinate it with the developers.

for now im using a built in api in postman REST API basics: CRUD, test & variable

{{base_url}} = https://postman-rest-api-learner.glitch.me/

Get data with params id = 1

{{base_url}}/info?id=1

Post data with the body of raw json

{

    "name":"Add your name in the body"

}

{{base_url}}/info

Update data

Delete data

// Get expected result from the data file

const expectedResult = pm.iterationData.get("expected_result");// 'Passed' or 'Failed'

// Get actual status code

const actualStatus = pm.response.code;

// Define what you consider a "Passed" status

const isActualPassed = actualStatus ===200|| actualStatus ===201;

// Convert actual result to 'Passed' or 'Failed'

const actualResult = isActualPassed ?"PASSED":"FAILED";

// Log details (optional, for debugging)

console.log("Scenario:", pm.iterationData.get("scenario"));

console.log("Expected Result:", expectedResult);

console.log("Actual Status:", actualStatus);

console.log("Actual Result:", actualResult);

// Perform the test

pm.test("Expected result matches actual result",function(){

    pm.expect(actualResult).to.eql(expectedResult);

});

// ✅ Test for expected status codes (optional: customize for your API)

// pm.test("Status code is 200 or 201 (Success)", function () {

//     pm.expect([200, 201]).to.include(actualStatus);

// });

// Convert the `payload_api1` object to a string so it's usable in raw JSON body

pm.variables.set("payload_Data_stringified",JSON.stringify(pm.iterationData.get("payload_Data")));



docs still IP
