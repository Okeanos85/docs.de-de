---
title: IValidator::Validate-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IValidator.Validate
api_location: mscoree.dll
api_type: COM
f1_keywords: Validate
helpviewer_keywords:
- IValidator::Validate method [.NET Framework hosting]
- Validate method, IValidator interface [.NET Framework hosting]
ms.assetid: 7d68666a-fb73-4455-bebd-908d49a16abc
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 722c6acc7e152a78ba28bc2730b2fdc7e0c45eb0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ivalidatorvalidate-method"></a><span data-ttu-id="5af9a-102">IValidator::Validate-Methode</span><span class="sxs-lookup"><span data-stu-id="5af9a-102">IValidator::Validate Method</span></span>
<span data-ttu-id="5af9a-103">Überprüft die angegebene Datei (portable Executable) oder Microsoft intermediate Language (MSIL)-Datei.</span><span class="sxs-lookup"><span data-stu-id="5af9a-103">Validates the specified portable executable (PE) or Microsoft intermediate language (MSIL) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5af9a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5af9a-104">Syntax</span></span>  
  
```  
HRESULT Validate (  
    [in] IVEHandler            *veh,  
    [in] IUnknown              *pAppDomain,  
    [in] unsigned long          ulFlags,  
    [in] unsigned long          ulMaxError,  
    [in] unsigned long          token,  
    [in] LPWSTR                 fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long          ulSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5af9a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5af9a-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="5af9a-106">[in] Ein Zeiger auf eine `IVEHandler` -Instanz, die Validierungsfehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="5af9a-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="5af9a-107">[in] Ein Zeiger auf die Anwendungsdomäne, in der die Datei geladen wird.</span><span class="sxs-lookup"><span data-stu-id="5af9a-107">[in] A pointer to the application domain in which the file is loaded.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="5af9a-108">[in] Eine bitweise Kombination von [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) Werte, der angibt, die Überprüfungen, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5af9a-108">[in] A bitwise combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the validations that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="5af9a-109">[in] Die maximale Anzahl von Fehlern, um zuzulassen, bevor Sie die Überprüfung beendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5af9a-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="5af9a-110">[in] Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="5af9a-110">[in] Not used.</span></span>  
  
 `fileName`  
 <span data-ttu-id="5af9a-111">[in] Eine Zeichenfolge, die den Namen der zu überprüfenden Datei angibt.</span><span class="sxs-lookup"><span data-stu-id="5af9a-111">[in] A string that specifies the name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="5af9a-112">[in] Ein Zeiger auf die Speicherpuffer in dem die Datei gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="5af9a-112">[in] A pointer to the memory buffer in which the file is stored.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="5af9a-113">[in] Die Größe in Bytes der Datei überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="5af9a-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5af9a-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5af9a-114">Requirements</span></span>  
 <span data-ttu-id="5af9a-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5af9a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5af9a-116">**Header:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="5af9a-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="5af9a-117">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5af9a-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5af9a-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5af9a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5af9a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5af9a-119">See Also</span></span>  
 