---
title: ICorDebugRegisterSet2::GetRegistersAvailable-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet2.GetRegistersAvailable
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet2::GetRegistersAvailable
helpviewer_keywords:
- GetRegistersAvailable method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegistersAvailable method [.NET Framework debugging]
ms.assetid: f3ed344b-0d3a-44e8-8000-2a97e0805a2c
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1f91b30b2ab50fc74049365d5c290bbaae1e20b6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugregisterset2getregistersavailable-method"></a><span data-ttu-id="829cf-102">ICorDebugRegisterSet2::GetRegistersAvailable-Methode</span><span class="sxs-lookup"><span data-stu-id="829cf-102">ICorDebugRegisterSet2::GetRegistersAvailable Method</span></span>
<span data-ttu-id="829cf-103">Ruft ein Array von Bytes, die eine Bitmap mit den verfügbaren Registern bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="829cf-103">Gets an array of bytes that provides a bitmap of the available registers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="829cf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="829cf-104">Syntax</span></span>  
  
```  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="829cf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="829cf-105">Parameters</span></span>  
 `numChunks`  
 <span data-ttu-id="829cf-106">[in] Die Größe des `availableRegChunks`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="829cf-106">[in] The size of the `availableRegChunks` array.</span></span>  
  
 `availableRegChunks`  
 <span data-ttu-id="829cf-107">[out] Ein Array von Bytes, von denen jedes Bit eines Registers entspricht.</span><span class="sxs-lookup"><span data-stu-id="829cf-107">[out] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="829cf-108">Wenn ein Registers verfügbar ist, wird die Registrierung entsprechende Bit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="829cf-108">If a register is available, the register's corresponding bit is set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="829cf-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="829cf-109">Remarks</span></span>  
 <span data-ttu-id="829cf-110">Die Werte der CorDebugRegister-Enumeration angeben die Register anderer Mikroprozessoren.</span><span class="sxs-lookup"><span data-stu-id="829cf-110">The values of the CorDebugRegister enumeration specify the registers of different microprocessors.</span></span> <span data-ttu-id="829cf-111">Die oberen fünf Bits Anteil jedes einzelnen Werts sind der Index in der `availableRegChunks` Bytearray.</span><span class="sxs-lookup"><span data-stu-id="829cf-111">The upper five bits of each value are the index into the `availableRegChunks` array of bytes.</span></span> <span data-ttu-id="829cf-112">Die unteren drei Bits der einzelnen Werte identifizieren die Bitposition innerhalb des indizierten Byte.</span><span class="sxs-lookup"><span data-stu-id="829cf-112">The lower three bits of each value identify the bit position within the indexed byte.</span></span> <span data-ttu-id="829cf-113">Erhält eine `CorDebugRegister` Wert, der angibt, ein bestimmtes Register, die Position des Registers in der Maske wird wie folgt bestimmt:</span><span class="sxs-lookup"><span data-stu-id="829cf-113">Given a `CorDebugRegister` value that specifies a particular register, the register's position in the mask is determined as follows:</span></span>  
  
1.  <span data-ttu-id="829cf-114">Extrahieren Sie Index benötigt Zugriff auf die richtige Byte in den `availableRegChunks` Array:</span><span class="sxs-lookup"><span data-stu-id="829cf-114">Extract the index needed to access the correct byte in the `availableRegChunks` array:</span></span>  
  
     <span data-ttu-id="829cf-115">`CorDebugRegister`Wert >> 3</span><span class="sxs-lookup"><span data-stu-id="829cf-115">`CorDebugRegister` value >> 3</span></span>  
  
2.  <span data-ttu-id="829cf-116">Extrahieren Sie die Bitposition innerhalb des indizierten Byte, in dem das niederwertigste Bit von Bit 0 (null) ist:</span><span class="sxs-lookup"><span data-stu-id="829cf-116">Extract the bit position within the indexed byte, where bit zero is the least significant bit:</span></span>  
  
     <span data-ttu-id="829cf-117">`CorDebugRegister`Wert & 7</span><span class="sxs-lookup"><span data-stu-id="829cf-117">`CorDebugRegister` value & 7</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="829cf-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="829cf-118">Requirements</span></span>  
 <span data-ttu-id="829cf-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="829cf-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="829cf-120">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="829cf-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="829cf-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="829cf-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="829cf-122">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="829cf-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="829cf-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="829cf-123">See Also</span></span>  
 [<span data-ttu-id="829cf-124">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="829cf-124">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 [<span data-ttu-id="829cf-125">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="829cf-125">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)