---
title: ICorDebugThread::GetID-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.GetID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::GetID
helpviewer_keywords:
- ICorDebugThread::GetID method [.NET Framework debugging]
- GetID method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: f1de4584-92df-42f3-9da4-fca03a1c6821
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 31ae48d62221d45a8457c304a1929886738190c4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadgetid-method"></a><span data-ttu-id="f8672-102">ICorDebugThread::GetID-Methode</span><span class="sxs-lookup"><span data-stu-id="f8672-102">ICorDebugThread::GetID Method</span></span>
<span data-ttu-id="f8672-103">Ruft das aktuelle Betriebssystembezeichner des aktiven Teils des ICorDebugThread ab.</span><span class="sxs-lookup"><span data-stu-id="f8672-103">Gets the current operating system identifier of the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8672-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8672-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f8672-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f8672-105">Parameters</span></span>  
 `pdwThreadId`  
 <span data-ttu-id="f8672-106">[out] Der Bezeichner des Threads.</span><span class="sxs-lookup"><span data-stu-id="f8672-106">[out] The identifier of the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8672-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f8672-107">Remarks</span></span>  
 <span data-ttu-id="f8672-108">Die Betriebssystem-ID während der Ausführung eines Prozesses ändern kann, und kann einen anderen Wert für die verschiedenen Teile des Threads.</span><span class="sxs-lookup"><span data-stu-id="f8672-108">The operating system identifier can potentially change during execution of a process, and can be a different value for different parts of the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8672-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f8672-109">Requirements</span></span>  
 <span data-ttu-id="f8672-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8672-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8672-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f8672-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8672-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8672-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8672-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8672-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>