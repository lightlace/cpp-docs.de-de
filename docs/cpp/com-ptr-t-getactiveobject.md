---
title: "_com_ptr_t::GetActiveObject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t.GetActiveObject"
  - "_com_ptr_t::GetActiveObject"
  - "GetActiveObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetActiveObject-Methode"
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# _com_ptr_t::GetActiveObject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Wird einer vorhandenen Instanz eines Objekts mit **CLSID** oder **ProgID** angefügt.  
  
## Syntax  
  
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
  
#### Parameter  
 `rclsid`  
 Die **CLSID** eines Objekts.  
  
 `clsidString`  
 Eine Unicode\-Zeichenfolge, die entweder eine **CLSID** \(beginnend mit "**{**"\) oder eine **ProgID** enthält.  
  
 `clsidStringA`  
 Eine Mehrbytezeichenfolge mit der ANSI\-Codepage, die entweder eine **CLSID** \(beginnend mit "**{**"\) oder eine **ProgID** enthält.  
  
## Hinweise  
 Diese Memberfunktionen rufen `GetActiveObject` auf, um einen Zeiger auf ein ausgeführtes Objekt abzurufen, das mit OLE registriert wurde und dann den Schnittstellentyp des intelligenten Zeigers abfragt.  Das Zeigerergebnis wird dann innerhalb dieses `_com_ptr_t`\-Objekts gekapselt.  **Release** wird aufgerufen, um den Verweiszähler für den zuvor gekapselten Zeiger zu verringern.  Diese Routine gibt `HRESULT` zurück, um einen Erfolg oder Fehler anzuzeigen.  
  
-   **GetActiveObject\(**  `rclsid`  **\)** Fügt sich einer vorhandenen Instanz eines Objekts an, dem eine **CLSID** gegeben wurde.  
  
-   **GetActiveObject\(**  `clsidString`  **\)** Fügt sich einer vorhandenen Instanz eines angegebenen Objekts an, dem eine Unicode\-Zeichenfolge gegeben wurde, die entweder eine **CLSID** \(beginnend mit "**{**"\) oder eine **ProgID** enthält.  
  
-   **GetActiveObject\(**  `clsidStringA`  **\)** Fügt sich einer vorhandenen Instanz eines angegebenen Objekts an, dem eine Multibytezeichenfolge gegeben wurde, die entweder eine **CLSID** \(beginnend mit "**{**"\) oder eine **ProgID** enthält.  Ruft [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072) auf, die davon ausgeht, dass die Zeichenfolge in der ANSI\-Codepage anstatt eine OEM\-Codepage ist.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_com\_ptr\_t\-Klasse](../cpp/com-ptr-t-class.md)