---
title: ICorDebugThread3::GetActiveInternalFrames-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread3.GetActiveInternalFrames Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread3::GetActiveInternalFrames
helpviewer_keywords:
- ICorDebugThread3::GetActiveInternalFrames method [.NET Framework debugging]
- GetActiveInternalFrames method [.NET Framework debugging]
ms.assetid: d69796b4-5b6d-457c-85f6-2cf42e8a8773
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9b94827ac49c69c5e72c2e300a80914774cc498
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugthread3getactiveinternalframes-method"></a><span data-ttu-id="b8a19-102">ICorDebugThread3::GetActiveInternalFrames-Methode</span><span class="sxs-lookup"><span data-stu-id="b8a19-102">ICorDebugThread3::GetActiveInternalFrames Method</span></span>
<span data-ttu-id="b8a19-103">Gibt ein Array von internen Frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) Objekte) auf dem Stapel.</span><span class="sxs-lookup"><span data-stu-id="b8a19-103">Returns an array of internal frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objects) on the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8a19-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8a19-104">Syntax</span></span>  
  
```  
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b8a19-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b8a19-105">Parameters</span></span>  
 `cInternalFrames`  
 <span data-ttu-id="b8a19-106">[in] Die Anzahl der erwarteten internen Frames `ppInternalFrames`.</span><span class="sxs-lookup"><span data-stu-id="b8a19-106">[in] The number of internal frames expected in `ppInternalFrames`.</span></span>  
  
 `pcInternalFrames`  
 <span data-ttu-id="b8a19-107">[out] Ein Zeiger auf eine `ULONG32` , enthält die Anzahl der internen Frames auf dem Stapel.</span><span class="sxs-lookup"><span data-stu-id="b8a19-107">[out] A pointer to a `ULONG32` that contains the number of internal frames on the stack.</span></span>  
  
 `ppInternalFrames`  
 <span data-ttu-id="b8a19-108">[in, out] Ein Zeiger auf die Adresse eines Arrays von internen Frames auf dem Stapel.</span><span class="sxs-lookup"><span data-stu-id="b8a19-108">[in, out] A pointer to the address of an array of internal frames on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b8a19-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b8a19-109">Return Value</span></span>  
 <span data-ttu-id="b8a19-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b8a19-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b8a19-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b8a19-111">HRESULT</span></span>|<span data-ttu-id="b8a19-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b8a19-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b8a19-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="b8a19-113">S_OK</span></span>|<span data-ttu-id="b8a19-114">Die [ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) Objekt wurde erfolgreich erstellt.</span><span class="sxs-lookup"><span data-stu-id="b8a19-114">The [ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) object was successfully created.</span></span>|  
|<span data-ttu-id="b8a19-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b8a19-115">E_INVALIDARG</span></span>|<span data-ttu-id="b8a19-116">`cInternalFrames`ist ungleich NULL und `ppInternalFrames` ist `null`, oder `pcInternalFrames` ist `null`.</span><span class="sxs-lookup"><span data-stu-id="b8a19-116">`cInternalFrames` is not zero and `ppInternalFrames` is `null`, or `pcInternalFrames` is `null`.</span></span>|  
|<span data-ttu-id="b8a19-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="b8a19-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="b8a19-118">`ppInternalFrames`ist kleiner als die Anzahl der internen Frames.</span><span class="sxs-lookup"><span data-stu-id="b8a19-118">`ppInternalFrames` is smaller than the count of internal frames.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="b8a19-119">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="b8a19-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8a19-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b8a19-120">Remarks</span></span>  
 <span data-ttu-id="b8a19-121">Interne Frames sind Datenstrukturen, die von der Runtime zum Speichern temporärer Daten auf dem Stapel abgelegt.</span><span class="sxs-lookup"><span data-stu-id="b8a19-121">Internal frames are data structures pushed onto the stack by the runtime to store temporary data.</span></span>  
  
 <span data-ttu-id="b8a19-122">Beim ersten Aufruf `GetActiveInternalFrames`, sollten Sie festlegen, die `cInternalFrames` Parameter auf 0 (null), und die `ppInternalFrames` Parameter auf null.</span><span class="sxs-lookup"><span data-stu-id="b8a19-122">When you first call `GetActiveInternalFrames`, you should set the `cInternalFrames` parameter to 0 (zero), and the `ppInternalFrames` parameter to null.</span></span> <span data-ttu-id="b8a19-123">Wenn `GetActiveInternalFrames` zuerst zurückgegeben wird, `pcInternalFrames` enthält die Anzahl der internen Frames auf dem Stapel.</span><span class="sxs-lookup"><span data-stu-id="b8a19-123">When `GetActiveInternalFrames` first returns, `pcInternalFrames` contains the count of the internal frames on the stack.</span></span>  
  
 <span data-ttu-id="b8a19-124">`GetActiveInternalFrames`Klicken Sie dann werden ein zweites Mal aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b8a19-124">`GetActiveInternalFrames` should then be called a second time.</span></span> <span data-ttu-id="b8a19-125">Übergeben Sie die richtige Anzahl (`pcInternalFrames`) in der `cInternalFrames` Parameter, und geben Sie einen Zeiger auf ein entsprechend skalierten Array in `ppInternalFrames`.</span><span class="sxs-lookup"><span data-stu-id="b8a19-125">You should pass the proper count (`pcInternalFrames`) in the `cInternalFrames` parameter, and specify a pointer to an appropriately sized array in `ppInternalFrames`.</span></span>  
  
 <span data-ttu-id="b8a19-126">Verwenden der [ICorDebugStackWalk:: GetFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) Stapelrahmen der Methode, um tatsächliche zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="b8a19-126">Use the [ICorDebugStackWalk::GetFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) method to return actual stack frames.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8a19-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b8a19-127">Requirements</span></span>  
 <span data-ttu-id="b8a19-128">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8a19-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8a19-129">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8a19-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8a19-130">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8a19-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8a19-131">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8a19-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8a19-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8a19-132">See Also</span></span>  
 [<span data-ttu-id="b8a19-133">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b8a19-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="b8a19-134">Debuggen</span><span class="sxs-lookup"><span data-stu-id="b8a19-134">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)