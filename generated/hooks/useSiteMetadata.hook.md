```ts

export interface SiteMetadata {
  title: string
  description: string
  siteUrl: string
  author: string
}

function useSiteMetadata(): SiteMetadata {
  const data = useStaticQuery(graphql`
    {
      site {
        siteMetadata {
          title
          description
          siteUrl
          author
        }
      }
    }
  `)

  // Return directly wanted data
  return data.site.siteMetadata
}

export default useSiteMetadata
```