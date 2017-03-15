---
title: "COM-Unterst&#252;tzung des Compilers | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe-Compiler, COM-Unterstützung"
  - "COM, Compilerunterstützung"
ms.assetid: 76a78442-f2a4-4985-9967-67e20773f847
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# COM-Unterst&#252;tzung des Compilers
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Der Visual C\+\+\-Compiler kann COM\(Component Object Model\)\-Typbibliotheken direkt lesen und den Inhalt in C\+\+\-Quellcode übersetzen, der in die Kompilierung aufgenommen werden kann.  Es sind Spracherweiterungen verfügbar, um die COM\-Programmierung auf der Clientseite zu erleichtern.  
  
 Durch Verwendung der [\#import\-Präprozessordirektive](../preprocessor/hash-import-directive-cpp.md) kann der Compiler eine Typbibliothek lesen und in eine C\+\+\-Headerdatei konvertieren, die die COM\-Schnittstellen als Klassen beschreibt.  Ein Satz von `#import`\-Attributen ist für die Benutzersteuerung des Inhalts der resultierenden Typbibliothek\-Headerdateien verfügbar.  
  
 Sie können das erweiterte [\_\_declspec](../cpp/declspec.md)\-Attribut [uuid](../cpp/uuid-cpp.md) verwenden, um einem COM\-Objekt einen GUID \(Globally Unique Identifier\) zuzuweisen.  Das Schlüsselwort [\_\_uuidof](../cpp/uuidof-operator.md) kann verwendet werden, um den GUID zu extrahieren, der einem COM\-Objekt zugeordnet ist.  Mit einem weiteren `__declspec`\-Attribut, [property](../cpp/property-cpp.md), können die **get**\- und **set**\-Methoden für einen Datenmember eines COM\-Objekts angegeben werden.  
  
 Ein Satz globale COM\-Unterstützungs\-Funktionen und \-Klassen wird bereitgestellt, um die **VARIANT**\- und `BSTR`\-Typen zu unterstützen, intelligente Zeiger zu implementieren und das Fehlerobjekt zu kapseln, das von `_com_raise_error` ausgelöst wird:  
  
-   [Globale COM\-Funktionen des Compilers](../cpp/compiler-com-global-functions.md)  
  
-   [\_bstr\_t](../cpp/bstr-t-class.md)  
  
-   [\_com\_error](../cpp/com-error-class.md)  
  
-   [\_com\_ptr\_t](../cpp/com-ptr-t-class.md)  
  
-   [\_variant\_t](../cpp/variant-t-class.md)  
  
## END Microsoft\-spezifisch  
  
## Siehe auch  
 [Compilerklassen für COM\-Unterstützung](../cpp/compiler-com-support-classes.md)   
 [Globale Funktionen des Compiler\-COM](../cpp/compiler-com-global-functions.md)