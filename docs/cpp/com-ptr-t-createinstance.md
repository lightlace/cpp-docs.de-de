---
title: _com_ptr_t::CreateInstance | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::CreateInstance
dev_langs:
- C++
helpviewer_keywords:
- CreateInstance method
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 1c07f7366c76c96580fc989475bd7f5ea23a38fe
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="comptrtcreateinstance"></a>_com_ptr_t::CreateInstance
**Microsoft-spezifisch**  
  
 Erstellt eine neue Instanz eines Objekts mit einem **CLSID** oder **ProgID**.  
  
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
 `rclsid`  
 Die **CLSID** eines Objekts.  
  
 `clsidString`  
 Eine Unicodezeichenfolge, die entweder eine **CLSID** (beginnend mit "**{**") oder ein **ProgID**.  
  
 `clsidStringA`  
 Eine mehrbytezeichenfolge mit der ANSI-Codepage, die entweder eine **CLSID** (beginnend mit "**{**") oder ein **ProgID**.  
  
 `dwClsContext`  
 Kontext für die Ausführung von ausführbarem Code.  
  
 `pOuter`  
 Die äußere unbekannte für [Aggregation](../atl/aggregation.md).  
  
## <a name="remarks"></a>Hinweise  
 Diese Memberfunktionen rufen `CoCreateInstance` auf, um ein neues COM-Objekt zu erstellen, und fragen dann den Schnittstellentyp dieses intelligenten Zeigers ab. Das Zeigerergebnis wird dann innerhalb dieses `_com_ptr_t`-Objekts gekapselt. **Version** wird aufgerufen, um den Verweiszähler für den zuvor gekapselten Zeiger zu verringern. Diese Routine gibt `HRESULT` zurück, um einen Erfolg oder Fehler anzuzeigen.  
  
-   **CreateInstance (** `rclsid` **,**`dwClsContext`**)** erstellt eine neue ausgeführte Instanz eines Objekts mit einem **CLSID**.        
  
-   **CreateInstance (** `clsidString` **,**`dwClsContext`**)** erstellt eine neue ausgeführte Instanz eines Objekts mit der eine Unicodezeichenfolge, die entweder eine **CLSID** (beginnend mit "**{**") oder ein **ProgID**.        
  
-   **CreateInstance (** `clsidStringA` **,**`dwClsContext`**)** erstellt eine neue ausgeführte Instanz eines Objekts mit einer Multibyte-Zeichenfolge, die entweder eine ** CLSID** (beginnend mit "**{**") oder ein **ProgID**.       Aufrufe [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072), die davon ausgeht, dass die Zeichenfolge in die ANSI-Codepage anstatt eine OEM-Codepage.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_ptr_t-Klasse](../cpp/com-ptr-t-class.md)
