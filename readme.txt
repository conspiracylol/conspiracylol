const fs = require("fs");

fs.readFile('conspiracy.json', 'utf8', (err, data) => {
    if (err) {
        console.error(err); // gracefully handle error
        return;
    }

    // Parse conspiracy.json
    let conspiracy = JSON.parse(data);
    conspiracy.age = 14;
    conspiracy.languages = "css, jss, html, node.js, python, c++, c#";
    conspiracy.interests = "reverse engineering, modding, swimming";
    conspiracy.location = "america";

    // Write the updated file.
    fs.writeFile('conspiracy.json', JSON.stringify(conspiracy), (err) => {
        if (err) {
            console.error(err); //catch errors
            return;
        }

        console.log('conspiracy.json updated!'); // Successfully updated conspiracy.json!
    });
});
