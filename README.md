# Cypress-commands

verifyDownload
cy.verifyDownload('CE_Guidance-on-posting-of-drivers.pdf', { timeout: 25000 });
cy.wait(500);


upload/attach file
const filepath = '407381.pdf'
cy.get('.cdk-overlay-container div div .mat-dialog-container .mat-form-field:nth-child(1) button').attachFile(filepath);
cy.wait(500);

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
