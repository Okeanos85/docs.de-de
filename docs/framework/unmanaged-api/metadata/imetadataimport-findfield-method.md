---
title: IMetaDataImport::FindField-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.FindField
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::FindField
helpviewer_keywords:
- IMetaDataImport::FindField method [.NET Framework metadata]
- FindField method [.NET Framework metadata]
ms.assetid: 38cd4e16-fbb2-471c-aa73-ac51a1931ad2
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2178f8738ca510fb2163c1043dd94ebcb7043904
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportfindfield-method"></a><span data-ttu-id="bf2ec-102">IMetaDataImport::FindField-Methode</span><span class="sxs-lookup"><span data-stu-id="bf2ec-102">IMetaDataImport::FindField Method</span></span>
<span data-ttu-id="bf2ec-103">Ruft einen Zeiger auf das FieldDef token für das Feld, das eingeschlossen ist durch das angegebene <xref:System.Type> und den angegebenen Namen und Metadaten aufweist.</span><span class="sxs-lookup"><span data-stu-id="bf2ec-103">Gets a pointer to the FieldDef token for the field that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf2ec-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bf2ec-104">Syntax</span></span>  
  
```  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bf2ec-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bf2ec-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="bf2ec-106">[in] Das TypeDef-Token für die Klasse oder Schnittstelle, die Suche nach Feld einschließt.</span><span class="sxs-lookup"><span data-stu-id="bf2ec-106">[in] The TypeDef token for the class or interface that encloses the field to search for.</span></span> <span data-ttu-id="bf2ec-107">Wenn dieser Wert ist `mdTokenNil`, erfolgt die Suche für eine globale Variable.</span><span class="sxs-lookup"><span data-stu-id="bf2ec-107">If this value is `mdTokenNil`, the lookup is done for a global variable.</span></span>  
  
 `szName`  
 <span data-ttu-id="bf2ec-108">[in] Der Name des zu suchenden Felds.</span><span class="sxs-lookup"><span data-stu-id="bf2ec-108">[in] The name of the field to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="bf2ec-109">[in] Ein Zeiger auf die binäre Metadatensignatur des Felds.</span><span class="sxs-lookup"><span data-stu-id="bf2ec-109">[in] A pointer to the binary metadata signature of the field.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="bf2ec-110">[in] Die Größe in Bytes des `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="bf2ec-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="bf2ec-111">[out] Ein Zeiger auf das übereinstimmende FieldDef-Token.</span><span class="sxs-lookup"><span data-stu-id="bf2ec-111">[out] A pointer to the matching FieldDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf2ec-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bf2ec-112">Remarks</span></span>  
 <span data-ttu-id="bf2ec-113">Geben Sie das Feld mit der einschließenden Klasse oder Schnittstelle (`td`), seinen Namen (`szName`), und optional die Signatur (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="bf2ec-113">You specify the field using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="bf2ec-114">Die Signatur zu übergeben, um `FindField` muss wurden im aktuellen Bereich generiert wurde, da Signaturen an einen bestimmten Bereich gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="bf2ec-114">The signature passed to `FindField` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="bf2ec-115">Eine Signatur kann ein Token einbetten, die die einschließende Klasse oder der angegebene Werttyp identifiziert.</span><span class="sxs-lookup"><span data-stu-id="bf2ec-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="bf2ec-116">(Das Token ist ein Index in die lokale TypeDef-Tabelle).</span><span class="sxs-lookup"><span data-stu-id="bf2ec-116">(The token is an index into the local TypeDef table).</span></span> <span data-ttu-id="bf2ec-117">Sie können keine Laufzeit-Signatur im Kontext des aktuellen Gültigkeitsbereichs erstellen und verwenden Sie diese Signatur als Eingabe für `FindField`.</span><span class="sxs-lookup"><span data-stu-id="bf2ec-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindField`.</span></span>  
  
 <span data-ttu-id="bf2ec-118">`FindField`Sucht nur Felder, die direkt in der Klasse oder Schnittstelle definiert wurden. Es werden geerbte Felder nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="bf2ec-118">`FindField` finds only fields that were defined directly in the class or interface; it does not find inherited fields.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf2ec-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bf2ec-119">Requirements</span></span>  
 <span data-ttu-id="bf2ec-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf2ec-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf2ec-121">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bf2ec-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bf2ec-122">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="bf2ec-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bf2ec-123">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf2ec-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf2ec-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf2ec-124">See Also</span></span>  
 [<span data-ttu-id="bf2ec-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bf2ec-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="bf2ec-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bf2ec-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)