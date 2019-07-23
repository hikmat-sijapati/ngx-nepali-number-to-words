# ngx-nepali-number-to-words
Angular package that converts number into Nepali words.

# Installation
Use Node Package Manager [npm](https://www.npmjs.com) to install ngx-nepali-number-to-words.
```
npm install ngx-nepali-number-to-words
``` 
# Supported Word Formats
Library supports two word formats.
```
enum WORD_FORMAT {
    TEXT = 'text',
    MONEY = 'money'
};
```
```text``` format displays number's corresponding Nepali words.

```money``` format displays number's corresponing words as Nepali moeny.

# Usage
Import `NgxNepaliNumberToWordsModule` in the root module(`AppModule`):
```typescript
// Import module
import {NgxNepaliNumberToWordsModule} from 'ngx-nepali-number-to-words';

@NgModule({
  imports: [
    // ...
    NgxNepaliNumberToWordsModule.forRoot()
  ]
})
export class AppModule {}
```
You can use `ngx-nepali-number-to-words` as both Angular `service` & `pipe`.

1. Using as Angular `service` in your component.

Component:
```typescript
//...
import { NgxNepaliNumberToWordsService } from 'ngx-nepali-number-to-words';

class AppComponent implements OnInit {
  constructor(private nepaliNumberToWordsService: NgxNepaliNumberToWordsService) {}
  
  ngOnInit() {
    console.log(this.NgxNepaliNumberToWordsService.toWords(10025)); //Output: दश हजार पच्चीस
    console.log(this.NgxNepaliNumberToWordsService.toWords(110263.23)); //Output: एक लाख दश हजार दुई सय त्रिसट्ठी दशमलब दुई तीन

    //To display words as Nepali Money just pass format parameter as money
    console.log(this.NgxNepaliNumberToWordsService.toWords(10025, 'money')); //Output: दश हजार पच्चीस रूपैयाँ
    console.log(this.NgxNepaliNumberToWordsService.toWords(110263.23), 'money');//Output: एक लाख दश हजार दुई सय त्रिसट्ठी रूपैयाँ दुई तीन पैसा

    //For Negative number
    console.log(this.NgxNepaliNumberToWordsService.toWords(-1234567));//Output: माइनस बाह्र लाख चौंतीस हजार पाँच सय सर्सठ्ठी
  }
}

2. Using as Angular `pipe` in your template.
```html
    <p>{{ 90945 | nepaliWords }}:</p>
    नब्बे हजार नौ सय पैंतालीस
    <p>{{ 90945 | nepaliWords: 'money' }}:</p>
    नब्बे हजार नौ सय पैंतालीस रूपैयाँ
```

## Creator

#### [Hikmat Sijapati](mailto:hikmatsijapati2014@gmail.com)

- [@GitHub](https://github.com/hikmat-sijapati)

### License
ngx-nepali-number-to-words is [MIT licensed](./LICENSE).
