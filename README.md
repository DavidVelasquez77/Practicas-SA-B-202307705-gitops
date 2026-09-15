# Practicas-SA-B-202307705-gitops

Repositorio declarativo de la aplicación ComicRent de la Práctica 8. ArgoCD observa `main` y sincroniza el chart `apps/comicrent` en `sa-p8`. El despliegue progresivo se realiza con Argo Rollouts en estrategia Canary.

- ArgoCD namespace: `argocd`
- Application: `comicrent-p8`
- Application namespace: `sa-p8`
- Chart: `apps/comicrent`
- Promotion: 10% → 25% → 50% → 100%
- Analysis: k6 smoke test con error 0% y p95 menor a 500 ms
- Secrets: credenciales versionadas únicamente como `SealedSecret` con `encryptedData`

La infraestructura GKE, ArgoCD, Argo Rollouts, Kyverno, Sealed Secrets, las
políticas y el `Application` de bootstrap pertenecen a Terraform en el repositorio
de código. Este repositorio no ejecuta pipelines ni aplica recursos al clúster.
