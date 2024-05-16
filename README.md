# Criando-o-Seu-Blog-Pessoal-Com-Next.js

Criação de um blog pessoal com Next.js, incluindo exemplos práticos e organizando o conteúdo em módulos. Vamos começar!

---

**Módulo 1: Introdução ao Next.js**
O Next.js é um framework poderoso baseado em React que permite a construção de aplicações web modernas com facilidade. Ele oferece funcionalidades como **renderização híbrida** (SSR e SSG), suporte a **TypeScript**, e um sistema de rotas eficiente.

**Exemplo Prático:**
```jsx
// pages/index.js
import Head from 'next/head'

export default function Home() {
  return (
    <div>
      <Head>
        <title>Meu Blog Pessoal</title>
        <meta name="description" content="Bem-vindo ao meu blog pessoal" />
      </Head>
      <main>
        <h1>Bem-vindo ao meu blog pessoal</h1>
      </main>
    </div>
  )
}
```

**Módulo 2: Estruturação do Blog**
A estrutura do seu blog é crucial. Utilize o sistema de rotas do Next.js para criar páginas estáticas para suas postagens, sobre mim, e contato.

**Exemplo Prático:**
```jsx
// pages/posts/[slug].js
import { useRouter } from 'next/router'

const Post = () => {
  const router = useRouter()
  const { slug } = router.query

  return <h1>Post: {slug}</h1>
}

export default Post
```

**Módulo 3: Dinamismo e Integração com a Nuvem**
Para tornar seu blog dinâmico, você pode integrá-lo com um CMS headless como o Contentful ou Strapi. Isso permitirá que você gerencie seu conteúdo de forma centralizada e segura.

**Exemplo Prático:**
```jsx
// lib/api.js
import { createClient } from 'contentful'

const client = createClient({
  space: process.env.CONTENTFUL_SPACE_ID,
  accessToken: process.env.CONTENTFUL_ACCESS_TOKEN,
})

export const getPosts = async () => {
  const entries = await client.getEntries({ content_type: 'blogPost' })
  return entries.items
}
```

**Módulo 4: Deploy e Serviços de Nuvem**
Finalmente, você pode fazer o deploy do seu blog em serviços de nuvem como Vercel ou Netlify, que oferecem integração direta com o GitHub e deploy contínuo.

**Exemplo Prático:**
```bash
# Comandos para deploy no Vercel
vercel login
vercel link
vercel deploy
```

---

Esses módulos cobrem os aspectos fundamentais para criar e lançar seu blog pessoal com Next.js. Cada módulo foi projetado para lhe dar uma compreensão prática e teórica, garantindo que você tenha todas as ferramentas necessárias para se destacar no mercado de front-end.
