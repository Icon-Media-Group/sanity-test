# Sanity CMS



## Installering

installer cli

```bash
npm install -g @sanity/cli
```

start nytt prosjekt

```bash
sanity init
```

kjør studio, først CD inn i prosjektet.

```bash
sanity start
```



## Opprett nytt schema

Oppretter nytt schema med:

- kursnavn
- kursID
- kategori

```javascript
import createSchema from 'part:@sanity/base/schema-creator'
import schemaTypes from 'all:part:@sanity/base/schema-type'

export default createSchema({
  name: 'kurs',
  types: schemaTypes.concat([
    {
      title: "Kurs",
      name: "kurs",
      type: "document",
        
      fields: [{

                title: "Kursnavn",
                name: "kursnavn",
                type: "string",
            },
            {
                title: "kursID",
                name: "kursID",
                type: "number"
            },
            {
                title: "kategori",
                name: "kategori",
                type: "string",
            }
        ]
    }])
})
```

![image-20201126093312685](C:\Users\mw109\AppData\Roaming\Typora\typora-user-images\image-20201126093312685.png)





## Redigering av felter og deployment

Endre Schemas og fields i schemas.js og deploy med:

```
sanity deploy
```





## Referanser til andre data

```javascript
{
  name: 'movie',
  type: 'object',
  fields: [
    {
      title: 'Director',
      name: 'director',
      type: 'reference',
      to: [{type: 'person'}]
    }
  ]
}
```

