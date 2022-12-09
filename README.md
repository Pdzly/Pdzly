```typescript
type languages = { [key: string]: { level: programmingLevel } };
enum programmingLevel {
  Newbie,
  Novice,
  Intermediate,
  Experienced,
  Professional,
}

interface Developer {
  Name: string;
  languagages: languages;
  programmingLanguages: languages;
  hobbies: string[];
}

class Rooki implements Developer {
  Name: string;
  languagages: languages;
  programmingLanguages: languages;
  hobbies: string[];
  constructor() {
    this.Name = "Rooki";
    this.languagages = {
      ["German"]: { level: programmingLevel.Professional },
      ["English"]: { level: programmingLevel.Intermediate },
    };
    this.programmingLanguages = {
      ["TS"]: { level: programmingLevel.Professional },
      ["JS"]: { level: programmingLevel.Experienced },
      ["C#"]: { level: programmingLevel.Experienced },
      ["(G)Lua"]: { level: programmingLevel.Intermediate },
      ["Python"]: { level: programmingLevel.Novice },
    };
    this.hobbies = [
      "Programming",
      "Tech Related Stuff",
      "(Crypto a little bit)",
      "Privacy",
    ];
  }

  async Introduce(){
    return `Hi all, 
    
    my Name is ${this.Name} and my Hobies are ${this.hobbies.join(", ")},
    
    My language experience: 
    ${Object.entries(this.languagages).map((([language, data]) => {
      return `${language}: ${data.level}\n`
    }))}

    My Programming Expertiese: 
    ${Object.entries(this.programmingLanguages).map((([language, data]) => {
      return `${language}: ${data.level}\n`
    }))}
    
    If you want to talk or chat just hit me up ;)`
  }
}
```
