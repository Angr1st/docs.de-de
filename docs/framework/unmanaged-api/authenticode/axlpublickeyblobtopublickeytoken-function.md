---
title: _AxlPublicKeyBlobToPublicKeyToken-Funktion
ms.date: 03/30/2017
api_name:
- _AxlPublicKeyBlobToPublicKeyToken
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 2d92a746-d68c-4f53-a16e-727f071a2d80
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37957931f9d1e2f8da44f70e5b99d3544bf0ae4f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497495"
---
# <a name="axlpublickeyblobtopublickeytoken-function"></a>_AxlPublicKeyBlobToPublicKeyToken-Funktion
Berechnet das öffentliche Schlüsseltoken für einen starken Namen aus einem CSP PUBLICKEYBLOB-Format.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT _AxlPublicKeyBlobToPublicKeyToken (  
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,  
    [out] LPWSTR                 *ppwszPublicKeyToken  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pCspPublicKeyBlob`  
 [in] Der Blob für den öffentlichen CSP-Schlüssel  
  
 `ppwszPublicKeyHash`  
 [out] Ein Zeiger auf WCHAR *, um den hexadezimal codierten Hash für den öffentlichen Schlüssel zu erhalten.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`, wenn die Funktion erfolgreich ausgeführt wird, sonst `S_FALSE`.  
  
## <a name="see-also"></a>Siehe auch
- [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
