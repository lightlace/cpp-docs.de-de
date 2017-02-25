---
title: "_bstr_t::copy | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_bstr_t::copy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BSTR-Objekt, copy"
  - "Copy-Methode"
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _bstr_t::copy
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Erstellt eine Kopie des gekapselten `BSTR`.  
  
## Syntax  
  
```  
  
      BSTR copy(  
  bool fCopy = true  
) const;  
```  
  
#### Parameter  
 `fCopy`  
 Bei **true** gibt **copy** eine Kopie des enthaltenden `BSTR` zurück; andernfalls gibt **copy** den tatsächlichen BSTR zurück.  
  
## Hinweise  
 Gibt eine neu zugeordnete Kopie des gekapselten `BSTR`\-Objekts zurück.  
  
## Beispiel  
  
```  
STDMETHODIMP CAlertMsg::get_ConnectionStr(BSTR *pVal){ //  m_bsConStr is _bstr_t  
   *pVal = m_bsConStr.copy();  
}  
```  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_bstr\_t\-Klasse](../cpp/bstr-t-class.md)