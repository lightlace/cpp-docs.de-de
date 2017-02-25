---
title: "Compilerwarnung C4687 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4687"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4687"
ms.assetid: 2f28e0b1-7358-4c88-bd70-aad8f0aa004c
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Compilerwarnung C4687
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Klasse': Eine versiegelte abstrakte Klasse kann keine Schnittstelle 'Schnittstelle' implementieren  
  
 Ein versiegelter abstrakter Datentyp ist normalerweise nur nützlich, um statische Memberfunktionen zu speichern.  
  
 Weitere Informationen finden Sie unter [abstract](../../windows/abstract-cpp-component-extensions.md) und unter [sealed](../../windows/sealed-cpp-component-extensions.md).  
  
 C4687 wird standardmäßig als Fehler ausgegeben.  Sie können C4687 mit dem [warning](../../preprocessor/warning.md)\-Pragma unterdrücken.  Wenn Sie bewusst eine Schnittstelle in einem versiegelten abstrakten Typ implementieren möchten, können Sie C4687 unterdrücken.  
  
## Beispiel  
 Im folgenden Beispiel wird C4687 generiert.  
  
```  
// C4687.cpp  
// compile with: /clr /c  
interface class A {};  
  
ref struct B sealed abstract : A {};   // C4687  
ref struct C sealed : A {};   // OK  
ref struct D abstract : A {};   // OK  
```