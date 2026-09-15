# Practicas-SA-B-202307705-gitops

Repositorio declarativo de la Práctica 8. ArgoCD observa `main` y sincroniza la aplicación `comicrent-p8` en `sa-p8`. El despliegue progresivo se realiza con Argo Rollouts en estrategia Canary.

- ArgoCD namespace: `argocd`
- Application: `comicrent-p8`
- Application namespace: `sa-p8`
- Chart: `apps/comicrent`
- Promotion: 10% → 25% → 50% → 100%
- Analysis: k6 smoke test con error 0% y p95 menor a 500 ms
- Policies: `p8-disallow-latest`, `p8-require-resources`, `p8-require-nonroot` y `p8-verify-cosign`, todas en `Enforce`
- Secrets: credenciales versionadas únicamente como `SealedSecret` con `encryptedData`
