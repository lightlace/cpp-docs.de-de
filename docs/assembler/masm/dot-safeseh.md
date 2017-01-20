---
title: ".SAFESEH"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - ".SAFESEH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "registering functions as exception handlers"
  - "SAFESEH directive"
  - ".SAFESEH directive"
ms.assetid: 6eaac8c4-c46f-47ae-8a66-f5cfeb267e43
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# .SAFESEH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Registriert eine Funktion als strukturierte Ausnahmehandler.  
  
## Syntax  
  
```  
  
.SAFESEH identifier  
```  
  
## Hinweise  
 *Bezeichner* muss die ID für Lokal definiertes [PROC](../../assembler/masm/proc.md) oder [EXTRN](../../assembler/masm/extrn.md) PROC sein.  [BEZEICHNUNG](../../assembler/masm/label-masm.md) ist nicht zulässig.  Die .SAFESEH\-Direktive erfordern die Befehlszeilenoption [\/safeseh](../../assembler/masm/ml-and-ml64-command-line-reference.md) ml.exe.  
  
 Weitere Informationen über strukturierte Ausnahmehandler finden Sie unter [\/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md).  
  
 Um beispielsweise einen sicheren Ausnahmehandler zu registrieren, erstellen Sie eine neue MASM\-Datei \(\) wie folgt mit \/safeseh zusammenstellen und fügen Sie es den verknüpften Objekten hinzu.  
  
```  
.386  
.model  flat  
MyHandler   proto  
.safeseh    MyHandler  
end  
```  
  
## Siehe auch  
 [Directives Reference](../../assembler/masm/directives-reference.md)