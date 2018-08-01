---
title: _com_ptr_t::CreateInstance | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::CreateInstance
dev_langs:
- C++
helpviewer_keywords:
- CreateInstance method [C++]
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 677d3dcab98b9bff8df7a49ba584900bd0b72925
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39407217"
---
# <a name="comptrtcreateinstance"></a>_com_ptr_t::CreateInstance
**Microsoft-spezifisch**  
  
 Erstellt eine neue Instanz eines angegebenen Objekts an eine `CLSID` oder `ProgID`.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CreateInstance(  
   const CLSID& rclsid,  
   IUnknown* pOuter=NULL,  
   DWORD dwClsContext = CLSCTX_ALL   
) throw( );  
HRESULT CreateInstance(  
   LPCWSTR clsidString,  
   IUnknown* pOuter=NULL,  
   DWORD dwClsContext = CLSCTX_ALL   
) throw( );  
HRESULT CreateInstance(  
   LPCSTR clsidStringA,  
   IUnknown* pOuter=NULL,  
   DWORD dwClsContext = CLSCTX_ALL   
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 *rclsid*  
 Die `CLSID` eines Objekts.  
  
 *clsidString*  
 Eine Unicode-Zeichenfolge, die entweder eine `CLSID` (beginnend mit "**{**") oder ein `ProgID`.  
  
 *clsidStringA*  
 Eine mehrbytezeichenfolge mit der ANSI-Codepage, die entweder eine `CLSID` (beginnend mit "**{**") oder ein `ProgID`.  
  
 *dwClsContext*  
 Kontext für die Ausführung von ausführbarem Code.  
  
 *pOuter*  
 Die äußere unbekannte für [Aggregation](../atl/aggregation.md).  
  
## <a name="remarks"></a>Hinweise  
 Diese Memberfunktionen rufen `CoCreateInstance` auf, um ein neues COM-Objekt zu erstellen, und fragen dann den Schnittstellentyp dieses intelligenten Zeigers ab. Das Zeigerergebnis wird dann innerhalb dieses `_com_ptr_t`-Objekts gekapselt. `Release` wird aufgerufen, um den Verweiszähler für den zuvor gekapselten Zeiger zu verringern. Diese Routine gibt zurück, das HRESULT, um den Erfolg oder Fehler anzuzeigen.  
  
-   **CreateInstance (***Rclsid* **,***DwClsContext***)** erstellt eine neue ausgeführte Instanz eines Objekts, dem ein `CLSID`.  
  
-   **CreateInstance (***ClsidString* **,***DwClsContext***)** erstellt eine neue ausgeführte Instanz eines angegebenen Objekts an eine Unicode-Zeichenfolge, die entweder eine `CLSID` (beginnend mit "**{**") oder ein `ProgID`.        
  
-   **CreateInstance (***ClsidStringA* **,***DwClsContext***)** erstellt eine neue ausgeführte Instanz eines angegebenen Objekts an eine Multibyte-Zeichenfolge, die entweder eine `CLSID` (beginnend mit "**{**") oder ein `ProgID`.       Aufrufe [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072), dem wird davon ausgegangen, dass die Zeichenfolge in die ANSI-Codepage anstatt eine OEM-Codepage.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_ptr_t-Klasse](../cpp/com-ptr-t-class.md)