---
title: ICorDebugProcess5::GetTypeFields-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.GetTypeFields
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::GetTypeFields
helpviewer_keywords:
- GetTypeFields method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeFields method [.NET Framework debugging]
ms.assetid: 6a0ad3ee-dacb-47e9-abae-4536bcc4804b
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7a64e754a77c7d730d921f8a8c1547dd18b66d77
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5gettypefields-method"></a><span data-ttu-id="18ebb-102">ICorDebugProcess5::GetTypeFields-Methode</span><span class="sxs-lookup"><span data-stu-id="18ebb-102">ICorDebugProcess5::GetTypeFields Method</span></span>
<span data-ttu-id="18ebb-103">Enthält Informationen zu den Feldern, die zu einem Typ gehören.</span><span class="sxs-lookup"><span data-stu-id="18ebb-103">Provides information about the fields that belong to a type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18ebb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="18ebb-104">Syntax</span></span>  
  
```  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],   
    [out] ULONG32 *pceltNeeded  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="18ebb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="18ebb-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="18ebb-106">[in] Der Bezeichner des Typs, dessen Feldinformationen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="18ebb-106">[in] The identifier of the type whose field information is retrieved.</span></span>  
  
 `celt`  
 <span data-ttu-id="18ebb-107">[in] Die Anzahl der [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) Objekte, deren Feldinformationen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="18ebb-107">[in] The number of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects whose field information is to be retrieved.</span></span>  
  
 `fields`  
 <span data-ttu-id="18ebb-108">[out] Ein Array von [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) Objekte, die Informationen über die Felder enthalten, die in den Typ gehören.</span><span class="sxs-lookup"><span data-stu-id="18ebb-108">[out] An array of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects that provide information about the fields that belong to the type.</span></span>  
  
 `pceltNeeded`  
 <span data-ttu-id="18ebb-109">[out] Ein Zeiger auf die Anzahl der [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) Objekttypen `fields`.</span><span class="sxs-lookup"><span data-stu-id="18ebb-109">[out] A pointer to the number of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects included in `fields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18ebb-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="18ebb-110">Remarks</span></span>  
 <span data-ttu-id="18ebb-111">Die `celt` -Parameter, der die Anzahl der Felder angibt, dessen Feldinformationen die Methode zum Auffüllen verwendet `fields`, sollte auf den Wert der entsprechen den `COR_TYPE_LAYOUT::numFields` Feld.</span><span class="sxs-lookup"><span data-stu-id="18ebb-111">The `celt` parameter, which specifies the number of fields whose field information the method uses to populate `fields`, should correspond to the value of the `COR_TYPE_LAYOUT::numFields` field.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18ebb-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="18ebb-112">Requirements</span></span>  
 <span data-ttu-id="18ebb-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18ebb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18ebb-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18ebb-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18ebb-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18ebb-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18ebb-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18ebb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18ebb-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18ebb-117">See Also</span></span>  
 [<span data-ttu-id="18ebb-118">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="18ebb-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="18ebb-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="18ebb-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)