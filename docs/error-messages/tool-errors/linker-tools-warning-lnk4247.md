---
title: "Linkertoolwarnung LNK4247"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4247"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4247"
ms.assetid: 085d7fdf-9eaf-4641-8473-6eaadd073c7b
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolwarnung LNK4247
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Einstiegspunkt 'decorated\_function\_name' hat bereits ein Threadattribut; 'Attribut' wird ignoriert  
  
 Ein mit [\/ENTRY \(Symbol für Einstiegspunkt\)](../../build/reference/entry-entry-point-symbol.md) angegebener Einstiegspunkt wies ein Threadattribut auf, obwohl gleichzeitig [\/CLRTHREADATTRIBUTE \(Festlegen des CLR\-Threadattributs\)](../../build/reference/clrthreadattribute-set-clr-thread-attribute.md) mit einem anderen Threadmodell angegeben wurde.  
  
 Der Linker hat den mit \/CLRTHREADATTRIBUTE angegebenen Wert ignoriert.  
  
 So vermeiden Sie diese Warnung:  
  
-   Entfernen Sie \/CLRTHREADATTRIBUTE aus dem Build.  
  
-   Entfernen Sie das Attribut aus der Quellcodedatei.  
  
-   Entfernen Sie das Attribut aus der Quelle und \/CLRTHREADATTRIBUTE aus dem Build, und verwenden Sie das Standard\-CLR\-Threadmodell.  
  
-   Ändern Sie den an \/CLRTHREADATTRIBUTE übergebenen Wert, sodass er mit dem Attribut in der Quelle übereinstimmt.  
  
-   Ändern Sie das Attribut in der Quelle, sodass es mit dem an \/CLRTHREADATTRIBUTE übergebenen Wert übereinstimmt.  
  
 Im folgenden Beispiel wird LNK4247 erzeugt  
  
```  
// LNK4247.cpp  
// compile with: /clr /c  
// post-build command: link /CLRTHREADATTRIBUTE:STA LNK4247.obj /entry:functionTitle /SUBSYSTEM:Console  
 [System::MTAThreadAttribute]  
void functionTitle (){}  
```