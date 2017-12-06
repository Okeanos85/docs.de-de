---
title: ICorDebugNativeFrame::GetLocalRegisterValue-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.GetLocalRegisterValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::GetLocalRegisterValue
helpviewer_keywords:
- GetLocalRegisterValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalRegisterValue method [.NET Framework debugging]
ms.assetid: 5ccb74f3-f891-430c-b70a-e370624edde2
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 43fdfc5cf4f17aaa9b26fc4a028c98c63a1b3c54
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframegetlocalregistervalue-method"></a><span data-ttu-id="96a6c-102">ICorDebugNativeFrame::GetLocalRegisterValue-Methode</span><span class="sxs-lookup"><span data-stu-id="96a6c-102">ICorDebugNativeFrame::GetLocalRegisterValue Method</span></span>
<span data-ttu-id="96a6c-103">Ruft den Wert eines Arguments oder einer lokalen Variablen, die im angegebenen Register für systemeigene Rahmen gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="96a6c-103">Gets the value of an argument or local variable that is stored in the specified register for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96a6c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="96a6c-104">Syntax</span></span>  
  
```  
HRESULT GetLocalRegisterValue (  
    [in]  CorDebugRegister   reg,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="96a6c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="96a6c-105">Parameters</span></span>  
 `reg`  
 <span data-ttu-id="96a6c-106">[in] Der Wert der "CorDebugRegister"-Enumeration, die die Registrierung mit dem Wert angibt.</span><span class="sxs-lookup"><span data-stu-id="96a6c-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="96a6c-107">[in] Eine ganze Zahl, die die Größe der binäre Metadatensignatur gibt an, welche die verweist die `pvSigBlob` Parameter.</span><span class="sxs-lookup"><span data-stu-id="96a6c-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="96a6c-108">[in] Ein `PCCOR_SIGNATURE` Wert, der auf die binäre Metadatensignatur der Typ des Werts verweist.</span><span class="sxs-lookup"><span data-stu-id="96a6c-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="96a6c-109">[out] Ein Zeiger auf die Adresse eines Objekts "ICorDebugValue", der den abgerufenen Wert, der im angegebenen Register gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="96a6c-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96a6c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="96a6c-110">Remarks</span></span>  
 <span data-ttu-id="96a6c-111">Die `GetLocalRegisterValue` Methode kann verwendet werden, entweder in einem systemeigenen Rahmen oder eine just-in-Time (JIT)-Frame kompiliert.</span><span class="sxs-lookup"><span data-stu-id="96a6c-111">The `GetLocalRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96a6c-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="96a6c-112">Requirements</span></span>  
 <span data-ttu-id="96a6c-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96a6c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96a6c-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96a6c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96a6c-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96a6c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96a6c-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96a6c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96a6c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96a6c-117">See Also</span></span>  
 