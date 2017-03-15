---
title: "_com_ptr_t::CreateInstance | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t::CreateInstance"
  - "_com_ptr_t.CreateInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateInstance-Methode"
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_ptr_t::CreateInstance
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Erstellt eine neue Instanz eines Objekts, dem ein **CLSID** oder **ProgID** übergeben wurde.  
  
## Syntax  
  
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
  
#### Parameter  
 `rclsid`  
 Die **CLSID** eines Objekts.  
  
 `clsidString`  
 Eine Unicode\-Zeichenfolge, die entweder eine **CLSID** \(beginnend mit "**{**"\) oder eine **ProgID** enthält.  
  
 `clsidStringA`  
 Eine Mehrbytezeichenfolge mit der ANSI\-Codepage, die entweder eine **CLSID** \(beginnend mit "**{**"\) oder eine **ProgID** enthält.  
  
 `dwClsContext`  
 Kontext für die Ausführung von ausführbarem Code.  
  
 `pOuter`  
 Die äußere Unbekannte für die [Aggregation](../atl/aggregation.md).  
  
## Hinweise  
 Diese Memberfunktionen rufen `CoCreateInstance` auf, um ein neues COM\-Objekt zu erstellen, und fragen dann den Schnittstellentyp dieses intelligenten Zeigers ab.  Das Zeigerergebnis wird dann innerhalb dieses `_com_ptr_t`\-Objekts gekapselt.  **Release** wird aufgerufen, um den Verweiszähler für den zuvor gekapselten Zeiger zu verringern.  Diese Routine gibt `HRESULT` zurück, um einen Erfolg oder Fehler anzuzeigen.  
  
-   **CreateInstance\(**  `rclsid` **,**  `dwClsContext`  **\)** Erstellt eine neue ausgeführte Instanz eines angegebenen Objekts, dem ein **CLSID** übergeben wurde.  
  
-   **CreateInstance\(**  `clsidString` **,**  `dwClsContext`  **\)** Erstellt eine neue ausgeführte Instanz eines Objekts, dem eine Unicode\-Zeichenfolge übergeben wurde, die entweder **CLSID** \(beginnend mit "**{**"\) oder **ProgID** enthält.  
  
-   **CreateInstance\(**  `clsidStringA` **,**  `dwClsContext`  **\)** Erstellt eine neue ausgeführte Instanz eines Objekts, dem eine Mehrfachzeichen\-Zeichenfolge übergeben wurde, die entweder **CLSID** \(beginnend mit "**{**"\) oder **ProgID** enthält.  Ruft [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072) auf, die davon ausgeht, dass die Zeichenfolge in der ANSI\-Codepage anstatt eine OEM\-Codepage ist.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_com\_ptr\_t\-Klasse](../cpp/com-ptr-t-class.md)