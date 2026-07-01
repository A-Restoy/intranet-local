# Portal Corporativo :: Restoy

Intranet corporativa de acceso interno: una página estática (`index.html`) con enlaces a las aplicaciones y recursos de la empresa, agrupados por categoría (Recursos Humanos, Técnico, Plataforma DevOps, Red Local).

## Vista previa

No requiere build ni dependencias. El estilo se carga desde el CDN de Tailwind CSS.

Abre `index.html` directamente en el navegador, o sirve el directorio con cualquier servidor estático, por ejemplo:

```bash
npx serve .
```

## Despliegue

El despliegue se gestiona con Gitea Actions (`.gitea/workflows/deploy.yml`). Cada push a `main` dispara un workflow que se ejecuta en un runner autoalojado (`rasberrypi`) y lanza el script de despliegue del servidor.
