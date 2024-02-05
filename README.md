# removeLeadingZeroFromString
Remove leading zeros from a string in JavaScript using regular expressions
## Synopsis
- worked for both format dd/mm/yyyy or  dd-mm-yyyy
Usage
-----
Basic form:

```ruby
 // Format dd/mm/yyyy
console.log(removeLeadingZeroFromDate("New York, NY 07/08/2025"));
console.log(removeLeadingZeroFromDate("New York, NY 07/11/2025"));
console.log(removeLeadingZeroFromDate("New York, NY 17/08/2025"));
console.log(removeLeadingZeroFromDate("New York, NY 07-08-2025"));
console.log(removeLeadingZeroFromDate("New York, NY 07-10-2025"));
console.log(removeLeadingZeroFromDate("New York, NY 17-08-2025"));

/**
 * remove leading zero from day and month
 */
function removeLeadingZeroFromDate(string){
    let expected = string.match(/\d{1,2}\D\d{1,2}\D(\d{4}|\d{2})/g);
    if (typeof expected == 'object' && expected != null) {
        let date = Object.values(expected)[0];
        let removeLeadingZero = Object.values(expected)[0].replace(/(^|-|\/)0+/g, "$1");
        let result = string.replace(date, removeLeadingZero);
        return result;
    }else return string;
}
 
```

