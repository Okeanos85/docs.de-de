---
title: IAssemblyName-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyName
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyName
helpviewer_keywords: IAssemblyName interface [.NET Framework fusion]
ms.assetid: f7f8e605-6b67-4151-936f-f04ecd671d90
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1d11889ab9db408b6e703bbaec17fd0487f142a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iassemblyname-interface"></a><span data-ttu-id="d9db5-102">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d9db5-102">IAssemblyName Interface</span></span>
<span data-ttu-id="d9db5-103">Stellt Methoden zum Beschreiben und Arbeiten mit eindeutige Identität einer Assembly bereit.</span><span class="sxs-lookup"><span data-stu-id="d9db5-103">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d9db5-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d9db5-104">Methods</span></span>  
  
|<span data-ttu-id="d9db5-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d9db5-105">Method</span></span>|<span data-ttu-id="d9db5-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9db5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d9db5-107">Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="d9db5-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-clone-method.md)|<span data-ttu-id="d9db5-108">Erstellt eine flache Kopie dieses `IAssemblyName` Objekt.</span><span class="sxs-lookup"><span data-stu-id="d9db5-108">Creates a shallow copy of this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="d9db5-109">Finalize-Methode</span><span class="sxs-lookup"><span data-stu-id="d9db5-109">Finalize Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-finalize-method.md)|<span data-ttu-id="d9db5-110">Dies ermöglicht `IAssemblyName` -Objekt, Ressourcen freizugeben und andere Bereinigungen durchzuführen, bevor der Destruktor aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="d9db5-110">Allows this `IAssemblyName` object to release resources and perform other cleanup operations before its destructor is called.</span></span>|  
|[<span data-ttu-id="d9db5-111">GetDisplayName-Methode</span><span class="sxs-lookup"><span data-stu-id="d9db5-111">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md)|<span data-ttu-id="d9db5-112">Ruft den lesbaren Namen der Assembly verwiesen wird, von diesem `IAssemblyName` Objekt.</span><span class="sxs-lookup"><span data-stu-id="d9db5-112">Gets the human-readable name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="d9db5-113">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="d9db5-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getname-method.md)|<span data-ttu-id="d9db5-114">Ruft den einfachen, unverschlüsselten Namen der Assemblyklasse von diesem `IAssemblyName` Objekt.</span><span class="sxs-lookup"><span data-stu-id="d9db5-114">Gets the simple, unencrypted name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="d9db5-115">GetProperty-Methode</span><span class="sxs-lookup"><span data-stu-id="d9db5-115">GetProperty Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getproperty-method.md)|<span data-ttu-id="d9db5-116">Ruft einen Zeiger auf die verwiesen wird, mit der angegebenen Eigenschaft `PropertyId`.</span><span class="sxs-lookup"><span data-stu-id="d9db5-116">Gets a pointer to the property referenced by the specified `PropertyId`.</span></span>|  
|[<span data-ttu-id="d9db5-117">GetVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="d9db5-117">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getversion-method.md)|<span data-ttu-id="d9db5-118">Ruft die Versionsinformationen für die Assembly verwiesen wird, von diesem `IAssemblyName` Objekt.</span><span class="sxs-lookup"><span data-stu-id="d9db5-118">Gets the version information for the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="d9db5-119">IsEqual-Methode</span><span class="sxs-lookup"><span data-stu-id="d9db5-119">IsEqual Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-isequal-method.md)|<span data-ttu-id="d9db5-120">Bestimmt, ob ein angegebener `IAssemblyName` Objekt gleich diesem `IAssemblyName`basierend auf den angegebenen Vergleichsflags.</span><span class="sxs-lookup"><span data-stu-id="d9db5-120">Determines whether a specified `IAssemblyName` object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>|  
|[<span data-ttu-id="d9db5-121">SetProperty-Methode</span><span class="sxs-lookup"><span data-stu-id="d9db5-121">SetProperty Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-setproperty-method.md)|<span data-ttu-id="d9db5-122">Legt den Wert der Eigenschaft verwiesen wird, durch das angegebene `PropertyId`.</span><span class="sxs-lookup"><span data-stu-id="d9db5-122">Sets the value of the property referenced by the specified `PropertyId`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d9db5-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d9db5-123">Requirements</span></span>  
 <span data-ttu-id="d9db5-124">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9db5-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9db5-125">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="d9db5-125">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d9db5-126">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9db5-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9db5-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9db5-127">See Also</span></span>  
 [<span data-ttu-id="d9db5-128">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d9db5-128">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="d9db5-129">IAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d9db5-129">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)