### code smells

# book-search.component.html:

- As per Industry standards the naming convention of variables should be meaningful which helps in better understanding of code.Fixed the same by replacing `b` with `book`.

- Using a function to format date can be avoided by replacing that with Angular's built in Date pipe. Angular pipes removes unnecessary calculations and DOM updates as the result is cached for same input (memoization) where as in case of methods, the calculations will happen every time when the template is rendered.

# book.search.component.ts:

-The subscription made on store.select() in ngOnInit() is never unsubscribed, this may lead to potential memory leak issue. Hence, added `async` pipe in the template which handles the unsubscription automatically.

# reading-list.component.html:

- As per Industry standards the naming convention of variables should be meaningful which helps in better understanding of code.Fixed the same by replacing `b` with `item`.


### Accessibility issues

# From Lighthouse report:

- Buttons do not have accessible names. Fixed it by adding `aria-label` attribute.

- Adjusted background and foreground colors to achieve sufficient contrast ratio between them. 

# Manually detected:

- Added `alt` attribute to `img` tags as it specifies an alternate text for image in case the image is not loaded.

- Added `aria-label` attribute with appropriate value in the elements wherever required to make accessible for screen readers.


### Imporovements

- For better user experience, a spinner can be added when awaiting API response.

- Appropriate error messages should be displayed to user in case of API failure. 

- Can make the application responive for smaller screens like mobiles and tablets by using media queries as it is a popular tailoring technique.

- To clear search results, clear button can be added in order to improve UX.
