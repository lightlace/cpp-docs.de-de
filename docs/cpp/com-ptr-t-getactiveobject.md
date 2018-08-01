---
title: _com_ptr_t::GetActiveObject | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::GetActiveObject
dev_langs:
- C++
helpviewer_keywords:
- GetActiveObject method [C++]
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 392460cde35096bc1c61db4d7e6bd2143932838d
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39403994"
---
# <a name="comptrtgetactiveobject"></a>_com_ptr_t::GetActiveObject
**Microsoft-spezifisch**  
  
 Fügt zu einer vorhandenen Instanz eines angegebenen Objekts an eine `CLSID` oder `ProgID`.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetActiveObject(  
   const CLSID& rclsid   
) throw( );  
HRESULT GetActiveObject(  
   LPCWSTR clsidString   
) throw( );  
HRESULT GetActiveObject(  
   LPCSTR clsidStringA   
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 *rclsid*  
 Die `CLSID` eines Objekts.  
  
 *clsidString*  
 Eine Unicode-Zeichenfolge, die entweder eine `CLSID` (beginnend mit "**{**") oder ein `ProgID`.  
  
 *clsidStringA*  
 Eine mehrbytezeichenfolge mit der ANSI-Codepage, die entweder eine `CLSID` (beginnend mit "**{**") oder ein `ProgID`.  
  
## <a name="remarks"></a>Hinweise  
 Diese Memberfunktionen rufen **GetActiveObject** um einen Zeiger auf ein ausgeführtes Objekt abzurufen, die mit OLE registriert wurde, und klicken Sie dann Abfragen für dieses intelligenten Zeigers Schnittstellentyp. Das Zeigerergebnis wird dann innerhalb dieses `_com_ptr_t`-Objekts gekapselt. `Release` wird aufgerufen, um den Verweiszähler für den zuvor gekapselten Zeiger zu verringern. Diese Routine gibt zurück, das HRESULT, um den Erfolg oder Fehler anzuzeigen.  
  
-   **GetActiveObject (**`rclsid`**)** fügt zu einer vorhandenen Instanz eines angegebenen Objekts an eine `CLSID`.  
  
-   **GetActiveObject (**`clsidString`**)** fügt sich einer vorhandenen Instanz eines Objekts, dem eine Unicodezeichenfolge, die entweder eine `CLSID` (beginnend mit "**{**") oder eine `ProgID`.  
  
-   **GetActiveObject (**`clsidStringA`**)** fügt zu einer vorhandenen Instanz eines Objekts, dem eine Multibyte-Zeichenfolge, die entweder eine `CLSID` (beginnend mit "**{**") oder ein `ProgID`. Aufrufe [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072), dem wird davon ausgegangen, dass die Zeichenfolge in die ANSI-Codepage anstatt eine OEM-Codepage.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_ptr_t-Klasse](../cpp/com-ptr-t-class.md)