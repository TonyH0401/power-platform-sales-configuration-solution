var Example = window.Example || {};
(function () {
  this.buttonOnClick = function (selectedControlSelectedItemIds, selectedControl) {
    console.log("Hello World 2");
    // Xrm.Utility.showProgressIndicator("Cloning process");
    selectedControlSelectedItemIds.forEach((element) => {
      const entityId = element;
      const execute_crff8_BoundAction_Request = {
        // Parameters
        entity: {
          entityType: "crff8_scaccount",
          // id: "61fb2530-0d1c-f011-998a-000d3aa12cf4",
          id: entityId,
        }, // entity

        getMetadata: function () {
          return {
            boundParameter: "entity",
            parameterTypes: {
              entity: {
                typeName: "mscrm.crff8_scaccount",
                structuralProperty: 5,
              },
            },
            operationType: 0,
            operationName: "crff8_BoundAction",
          };
        },
      };

      Xrm.WebApi.execute(execute_crff8_BoundAction_Request)
        .then(function success(response) {
          if (response.ok) {
            return response.json();
          }
        })
        .then(function (responseBody) {
          const result = responseBody;
          console.log(result);
          // Return Type: mscrm.crff8_BoundActionResponse
          // Output Parameters
          selectedControl.refresh();
          const output = result["output"]; // Edm.String
          console.log(output);
        })
        .catch(function (error) {
          console.log(error.message);
        });
    });
  };
}).call(Example);
