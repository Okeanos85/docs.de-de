---
title: ICLRStrongName::StrongNameTokenFromPublicKey-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameTokenFromPublicKey
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameTokenFromPublicKey
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey method [.NET Framework hosting]
- StrongNameTokenFromPublicKey method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 7962ce88-7e86-4a6f-8298-621b01ffc3c2
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 84f47fcef7c896b197de410234694c211d07c30b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a><span data-ttu-id="976bf-102">ICLRStrongName::StrongNameTokenFromPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="976bf-102">ICLRStrongName::StrongNameTokenFromPublicKey Method</span></span>
<span data-ttu-id="976bf-103">Ruft ein Token, das einen öffentlichen Schlüssel darstellt.</span><span class="sxs-lookup"><span data-stu-id="976bf-103">Gets a token that represents a public key.</span></span> <span data-ttu-id="976bf-104">Ein starker Name-Token ist die Kurzform eines öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="976bf-104">A strong name token is the shortened form of a public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="976bf-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="976bf-105">Syntax</span></span>  
  
```  
HRESULT StrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="976bf-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="976bf-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="976bf-107">[in] Eine Struktur des Typs [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) , enthält den öffentlichen Teil des Schlüsselpaars verwendet, um die Signatur mit starkem Namen generieren.</span><span class="sxs-lookup"><span data-stu-id="976bf-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="976bf-108">[in] Die Größe in Bytes, der `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="976bf-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="976bf-109">[out] Entspricht dem Schlüssel Token mit starkem Namen übergeben `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="976bf-109">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="976bf-110">Die common Language Runtime ordnet den Arbeitsspeicher, in dem das Token zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="976bf-110">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="976bf-111">Der Aufrufer muss diesen Arbeitsspeicher freigeben, mithilfe der [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="976bf-111">The caller must free this memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="976bf-112">[out] Die Größe in Bytes, des Tokens zurückgegebenen starken Namen.</span><span class="sxs-lookup"><span data-stu-id="976bf-112">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="976bf-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="976bf-113">Return Value</span></span>  
 <span data-ttu-id="976bf-114">`S_OK`Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [häufig auftretende HRESULT-Werte](http://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="976bf-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="976bf-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="976bf-115">Remarks</span></span>  
 <span data-ttu-id="976bf-116">Ein starker Name-Token ist die Kurzform eines öffentlichen Schlüssels, der verwendet wird, um Platz zu sparen, wenn wichtige Informationen in den Metadaten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="976bf-116">A strong name token is the shortened form of a public key that is used to save space when storing key information in metadata.</span></span> <span data-ttu-id="976bf-117">Insbesondere sind starken Namenstoken in Assemblyverweise verwendet, um auf die abhängige Assembly zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="976bf-117">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="976bf-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="976bf-118">Requirements</span></span>  
 <span data-ttu-id="976bf-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="976bf-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="976bf-120">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="976bf-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="976bf-121">**Bibliothek:** als Ressource in mscoree.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="976bf-121">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="976bf-122">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="976bf-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="976bf-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="976bf-123">See Also</span></span>  
 [<span data-ttu-id="976bf-124">StrongNameGetPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="976bf-124">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)  
 [<span data-ttu-id="976bf-125">PublicKeyBlob-Struktur</span><span class="sxs-lookup"><span data-stu-id="976bf-125">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 [<span data-ttu-id="976bf-126">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="976bf-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)