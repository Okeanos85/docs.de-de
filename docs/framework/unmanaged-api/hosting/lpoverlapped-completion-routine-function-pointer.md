---
title: LPOVERLAPPED_COMPLETION_ROUTINE-Funktionszeiger
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LPOVERLAPPED_COMPLETION_ROUTINE
api_location: mscoree.dll
api_type: COM
f1_keywords: LPOVERLAPPED_COMPLETION_ROUTINE
helpviewer_keywords: LPOVERLAPPED_COMPLETION_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 5fb645d9-b818-401c-8c2c-c30d86de58ba
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4d50f2058796d4c5c900474cdcbe71d8a5a911ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="lpoverlappedcompletionroutine-function-pointer"></a><span data-ttu-id="2e1b5-102">LPOVERLAPPED_COMPLETION_ROUTINE-Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="2e1b5-102">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>
<span data-ttu-id="2e1b5-103">Zeigt auf eine Funktion, die den Host benachrichtigt, wenn eine überlappende (d. h. asynchrone) E/A auf einem Gerät abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="2e1b5-103">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 <span data-ttu-id="2e1b5-104">Diese Funktionszeiger ist veraltet die [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e1b5-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e1b5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2e1b5-105">Syntax</span></span>  
  
```  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2e1b5-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2e1b5-106">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="2e1b5-107">[in] Ein Wert, der einen Fehlercode ist, wenn das Gerät geschlossen wurde. Dieser Wert ist, andernfalls 0 (null).</span><span class="sxs-lookup"><span data-stu-id="2e1b5-107">[in] A value that is an error code if the device has been closed; otherwise, this value is zero.</span></span>  
  
 <span data-ttu-id="2e1b5-108">Schließen eines Geräts führt dazu, dass alle ausstehenden e/a auf das Gerät sofort abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="2e1b5-108">Closing a device causes all pending I/O to the device to be completed immediately.</span></span>  
  
 `dwNumberOfBytesTransfered`  
 <span data-ttu-id="2e1b5-109">[in] Die Anzahl der Bytes, die von der e/a-Operation übertragen.</span><span class="sxs-lookup"><span data-stu-id="2e1b5-109">[in] The number of bytes transferred by the I/O operation.</span></span>  
  
 `lpOverlapped`  
 <span data-ttu-id="2e1b5-110">[in] Ein Zeiger auf eine Struktur, die Informationen enthält, die verwendet werden, um die e/a-Anforderung abgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2e1b5-110">[in] A pointer to a structure that contains information to be used to complete the I/O request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e1b5-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2e1b5-111">Remarks</span></span>  
 <span data-ttu-id="2e1b5-112">Die Funktion, die die `LPOVERLAPPED_COMPLETION_ROUTINE` Punkt ist eine Rückruffunktion und muss vom Writer der Hostinganwendung implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="2e1b5-112">The function to which `LPOVERLAPPED_COMPLETION_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="2e1b5-113">Die Rückruffunktion kann der Host die abgeschlossene e/a-Anforderung zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="2e1b5-113">The callback function allows the host to process the completed I/O request.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e1b5-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2e1b5-114">Requirements</span></span>  
 <span data-ttu-id="2e1b5-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e1b5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e1b5-116">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2e1b5-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2e1b5-117">**Bibliothek:** "Mscorwks.dll"</span><span class="sxs-lookup"><span data-stu-id="2e1b5-117">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="2e1b5-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e1b5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e1b5-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e1b5-119">See Also</span></span>  
 [<span data-ttu-id="2e1b5-120">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="2e1b5-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)