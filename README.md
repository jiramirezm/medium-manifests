# Vault CSI Driver ( Vault CSI Driver )
You might have already guessed the context of this article. Well, however, to provide a use case on the CSI driver let us assume that there are certain secrets that are to be mounted to the Pod as an ephemeral volume. Usually, in this case, you may have to create a Kubernetes secret by getting the values from Vault and then Mounting it to the Pod. This is very complicated. How about a solution where we can easily create this using a CRD and then Mount it to the Pod? Imagine having the flexibility to control the Pod’s lifecycle till the secrets are retrieved? Yes, getting Vault Secrets through Container Storage Interface (CSI) Volume is possible. The CSI Secrets Store driver allows users to create SecretProviderClass objects. This object defines which secret provider to use and what secrets to retrieve. When pods requesting CSI volumes are created, the CSI Secrets Store driver will send the request to the Vault CSI Provider if the provider is vault. The Vault CSI Provider will then use Secret Provider Class specified and the pod's service account to retrieve the secrets from Vault, and mount them into the pod's CSI volume.

The secret is retrieved from Vault and populated to the CSI secrets store volume during the ContainerCreation phase. This means that pods will be blocked from starting until the secrets have been read from Vault and written to the volume.

Full Article Published here 
https://pavan1999-kumar.medium.com/hashicvault-secrets-in-kubernetes-with-csi-driver-ec917d4a2672
