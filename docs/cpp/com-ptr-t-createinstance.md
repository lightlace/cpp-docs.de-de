---
title: _com_ptr_t::CreateInstance | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_ptr_t::CreateInstance
dev_langs: C++
helpviewer_keywords: CreateInstance method [C++]
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e4764cf615bf04e9f2b1c3c816becc5a58da35f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
  
-   **CreateInstance (** `clsidStringA` **,**`dwClsContext`**)** erstellt eine neue ausgeführte Instanz eines Objekts mit einer Multibyte-Zeichenfolge, die entweder eine  **CLSID** (beginnend mit "**{**") oder ein **ProgID**. Aufrufe [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072), die davon ausgeht, dass die Zeichenfolge in die ANSI-Codepage anstatt eine OEM-Codepage.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_ptr_t-Klasse](../cpp/com-ptr-t-class.md)