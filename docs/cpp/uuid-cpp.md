---
title: "uuid (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "uuid"
  - "uuid_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec-Schlüsselwort [C++], uuid"
  - "uuid __declspec-Schlüsselwort"
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# uuid (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Der Compiler fügt eine GUID an eine Klasse oder Struktur an, die mit dem `uuid`\-Attribut deklariert oder definiert ist \(nur vollständige COM\-Objektdefinitionen\).  
  
## Syntax  
  
```  
  
__declspec( uuid("  
ComObjectGUID  
") ) declarator  
```  
  
## Hinweise  
 Das `uuid`\-Attribut nimmt eine Zeichenfolge als sein Argument an.  Diese Zeichenfolge gibt eine GUID im normalen Registrierungsformat mit oder ohne die Trennzeichen **{ }** an.  Beispiel:  
  
```  
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) IUnknown;  
struct __declspec(uuid("{00020400-0000-0000-c000-000000000046}")) IDispatch;  
```  
  
 Dieses Attribut kann in einer Neudeklaration angewendet werden.  Auf diese Weise können die Systemheader die Definitionen von Schnittstellen bereitstellen, wie **IUnknown**, und die Neudeklaration in einem anderen Header \(z. B. COMDEF.H\) zum Angeben der GUID ist ebenfalls möglich.  
  
 Das Schlüsselwort [\_\_uuidof](../cpp/uuidof-operator.md) kann angewendet werden, um die konstante GUID abzurufen, welche an einen benutzerdefinierten Typ angefügt ist.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)