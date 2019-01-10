# Manage Tokens - Selection List

## Use Cases

### Display complete token list
As an user I want to be able to see all tokens that I have enabled and that are available.
<details>
  <summary>Acceptance Criteria</summary>

  * The content (token list) should start loading automatically
  * All selected tokens should be displayed alphabetically in a separate section before all available tokens
  * All available tokens should be displayed after the selected tokens.
    * It should be possible to display an unlimited number of tokens in the list (paginated list)
    * The next page of tokens should be loaded automatically when scrolling close to the end of the list
    * It should be indicated that data is loading
  * For each token we display the details
    * Icon
    * Name
    * Symbol
    * Enabled or not
  * It should be possible to select or deselect a token
    * Selecting a token should add it to the section of selected tokens
    * Deselecting a token should remove  it from the section of selected tokens

</details>

<details>
  <summary>iOS Screens</summary>
  
  TDB
</details>

<details>
  <summary>Android Screens</summary>
  
  * Loaded list: https://zpl.io/aRqlmBe
  * Loading data: TBD
</details>

### Could not load initial token list
As a user I want to be able to see all tokens that I have enabled even if the available tokens could not be loaded.
<details>
  <summary>Acceptance Criteria</summary>
  
  * An non-blocking error should be displayed to the user that the data could not be loaded
  * It should be possible to retrigger the loading of the available tokens
  * All enabled tokens should still be displayed
    * It should still be possible to deselect a token
  * Based on [Display complete token list](#display-complete-token-list)
</details>
<details>
  <summary>iOS Screens</summary>
  TDB
</details>
<details>
  <summary>Android Screens</summary>
  TDB
</details>

### Could not load next page of token list
As a user I want to be able to continue loading pages after a loading error occured.
<details>
  <summary>Acceptance Criteria</summary>
  
  * An non-blocking error should be displayed to the user that the data could not be loaded
  * It should be possible to retrigger the loading of the next token page
    * We should continue loading where we left off
    * Loaded tokens should not be reloaded
  * Based on [Display complete token list](#display-complete-token-list)
</details>
<details>
  <summary>iOS Screens</summary>
  TDB
</details>
<details>
  <summary>Android Screens</summary>
  TDB
</details>
