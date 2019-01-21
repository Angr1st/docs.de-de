---
title: IXCLRDataMethodInstance-Schnittstelle
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodInstance Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance Interface
helpviewer.keywords:
- IXCLRDataMethodInstance Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 5bf724bc76591ae59c073b5b9a788ca065f51dc0
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416389"
---
# <a name="ixclrdatamethodinstance-interface"></a><span data-ttu-id="d219f-102">IXCLRDataMethodInstance-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d219f-102">IXCLRDataMethodInstance Interface</span></span>

<span data-ttu-id="d219f-103">Stellt Methoden zum Abfragen von Informationen zu einer Methodeninstanz bereit.</span><span class="sxs-lookup"><span data-stu-id="d219f-103">Provides methods for querying information about a method instance.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="d219f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d219f-104">Methods</span></span>

| <span data-ttu-id="d219f-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d219f-105">Method</span></span>                                                                                                                  | <span data-ttu-id="d219f-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d219f-106">Description</span></span>                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [<span data-ttu-id="d219f-107">GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="d219f-107">GetILAddressMap</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-getiladdressmap-method.md) | <span data-ttu-id="d219f-108">Ruft den IL-Code mit Adressinformationen für die Zuordnung ab.</span><span class="sxs-lookup"><span data-stu-id="d219f-108">Gets the IL to address mapping information.</span></span> |

## <a name="remarks"></a><span data-ttu-id="d219f-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d219f-109">Remarks</span></span>

<span data-ttu-id="d219f-110">Diese Schnittstelle befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="d219f-110">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="d219f-111">Es ist jedoch eine COM-Schnittstelle, die von abgeleitet `IUnknown` mit GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` , die über die üblichen Mechanismen der COM-abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="d219f-111">However, it's a COM interface that derives from `IUnknown` with GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="d219f-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d219f-112">Requirements</span></span>

<span data-ttu-id="d219f-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d219f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="d219f-114">**Header:** Keine</span><span class="sxs-lookup"><span data-stu-id="d219f-114">**Header:** None</span></span>  
<span data-ttu-id="d219f-115">**Bibliothek:** Keine</span><span class="sxs-lookup"><span data-stu-id="d219f-115">**Library:** None</span></span>  
<span data-ttu-id="d219f-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d219f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="d219f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d219f-117">See Also</span></span>

- [<span data-ttu-id="d219f-118">Debuggen</span><span class="sxs-lookup"><span data-stu-id="d219f-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="d219f-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d219f-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)