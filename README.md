# Cypress-commands

verifyDownload
cy.verifyDownload('CE_Guidance-on-posting-of-drivers.pdf', { timeout: 25000 });
cy.wait(500);

sau
      cy.get(input[type=file]).selectFile('cypress/fixtures/blank.jpeg', { force: true });


upload/attach file
const filepath = '407381.pdf'
cy.get('.cdk-overlay-container div div .mat-dialog-container .mat-form-field:nth-child(1) button').attachFile(filepath);
cy.wait(500);

sau

cy.fixture('Chemari.xlsx', 'binary')
            .then(Cypress.Blob.binaryStringToBlob)
            .then(fileContent => {
                cy.get(importExcelSelectors.IMPORT_BTN).attachFile({
                    fileContent,
                    fileName: 'Chemari.xlsx',
                    mimeType: 'application/vnd.openxmlformats-officedocument.spreadsheetml.sheet',
                    encoding: 'utf8'
                })
            })

check mark
cy.get('[type="checkbox"]').check({ force: true }).should('be.checked');



click on the next button for more times
times(5, () => {
            cy.get('.mat-paginator-navigation-next')
              .click()
          })

timesout
commonMethods.clickOnTheFirstElement(usualSelectors.FILE_LINK, { timeout: 100000, interval: 500 });
        cy.wait(10000);
        
enter
commonMethods.typeTextInToaDom(usualSelectors.SELECT_TRAILER, 'CJ-13-RDE{enter}');
        cy.wait(5000);

select from menu
 cy.get('#options-header-menu').contains('1. Accounts').next('#view-one').then($el => {
            cy.wrap($el).invoke('show')
            cy.get('#b2b-users-menu-btn').click({ force: true })
        });


Conditional testing on checkbox in Cypress

a) cy
        .get(customerSelectors.BLOCKED_ORDERS)
        .as('blocked-checkbox')
        .invoke('is', ':checked')
        .then(checked => {
          if (checked) {
            cy
              .get('@blocked-checkbox')
              .click();
          } else {
            cy
              .get('@blocked-checkbox')
              .dblclick();
          }
        });
        
  b)  cy
        .get(normalSegmentationSelectors.CHECKBOX_SUBREGION)
        .as('dislocation-checkbox')
        .invoke('is', ':checked')
        .then(checked => {
            if (checked) {
                cy
                    .get('@dislocation-checkbox')
                    .should('be.checked')
            } else {
                cy
                    .get('@dislocation-checkbox')
                    .click();
            }
        });
       
 c)  cy
        .then(checked => {
         if (checked) {
             cy
               .get('#pop-up-attention-error').contains(normalSegmentationSelectors.WARNING_SAME_DELIVERY_ADDRESS)
               .get('#pop-up-ok-attention-error button')
               .click()
               .wait(20000)
                .get(normalSegmentationSelectors.CONFIRM_RELOCATION)
                .contains(normalSegmentationSelectors.CONFIRM_RELOCATION_TEXT)
          } else {
               cy
                 .wait(20000)
                 .get(normalSegmentationSelectors.CONFIRM_RELOCATION)
                 .contains(normalSegmentationSelectors.CONFIRM_RELOCATION_TEXT)
                }
            });


Dropdown
        cy.get(casaexpeditiiSelectors.DROPDOWN_SUBREGION).contains('Expeditii Cluj').click();
        
click on the first element        
            clickOnTheFirstElement(webElement) {
        cy.get(webElement).first().click({ force: true }, { timeout: 100000, interval: 500 });
    };

