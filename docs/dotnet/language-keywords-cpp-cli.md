---
title: "Sprachschl&#252;sselw&#246;rter (C++/CLI)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Schlüsselwörter [C++]"
ms.assetid: 021013b2-70ac-4df9-aa77-4af1c67a1a67
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Sprachschl&#252;sselw&#246;rter (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verschiedene Schlüsselwörter haben sich in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] gegenüber Managed Extensions for C\+\+ geändert.  
  
 In der neuen [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] \-Syntax wurde der doppelte Unterstrich entfernt, der allen Schlüsselwörtern vorangestellt war. Die einzige Ausnahme bildet das Schlüsselwort `__identifier`, bei dem der Unterstrich erhalten bleibt.  Eine Eigenschaft wird jetzt z. B. nicht mehr als `__property`, sondern als `property` deklariert.  
  
 Es gab zwei Hauptgründe für die Verwendung das doppelten Unterstrichs als Präfix in Managed Extensions:  
  
-   Es handelt sich um die konforme Methode zum Bereitstellen lokaler Erweiterungen für den ISO\-C\+\+\-Standard.  Eines der Hauptziele beim Design von Managed Extensions bestand darin, Inkompatibilitäten mit der Standardsprache, z. B. neue Schlüsselwörter oder Tokens, zu vermeiden.  Dies war der Hauptgrund dafür, die Zeigersyntax für die Deklaration von Objekten von verwalteten Referenztypen zu verwenden.  
  
-   Neben dem Konformitätsaspekt garantiert die Verwendung des doppelten Unterstrichs, dass keine Konflikte mit der vorhandenen CodeBase der Sprachenbenutzer auftreten.  Dies war das zweite Hauptziel beim Design von Managed Extensions.  
  
 Trotz der Entfernung der doppelten Unterstriche fühlt sich Microsoft weiterhin der Konformität verpflichtet.  Die Unterstützung für das dynamische Objektmodell der CLR stellt jedoch ein neues und leistungsfähiges Programmierparadigma dar.  Dieses neue Paradigma erfordert eigene Schlüsselwörter und Token auf hoher Ebene.  Wir haben versucht, eine erstklassige Ausdrucksmöglichkeit für dieses neue Paradigma zu finden und es gleichzeitig zu integrieren und die Standardsprache zu unterstützen.  Das neue Syntaxdesign bietet ein erstklassiges Programmiererlebnis dieser beiden verschiedenen Objektmodelle.  
  
 Ebenso haben wir große Anstrengungen unternommen, Nebenwirkungen und Konflikte bei der Einführung dieser neuen Schlüsselwörter zu vermeiden.  Dies wurde erreicht durch die Verwendung von Kontextschlüsselwörtern sowie von Schlüsselwörtern, die durch Leerzeichen getrennt sind.  Bevor wir die neue Syntax genauer betrachten, möchten wir diese beiden besonderen Varianten von Schlüsselwörtern erläutern.  
  
 Ein Kontextschlüsselwort hat innerhalb bestimmter Programmkontexte eine besondere Bedeutung.  So wird z. B. `sealed` im allgemeinen Programm als normaler Bezeichner behandelt.  Wenn es jedoch im Deklarationsteil eines verwalteten Referenzklassentyps auftritt, wird es als Schlüsselwort im Kontext dieser Klassendeklaration behandelt.  Auf diese Weise werden mögliche Nebenwirkungen durch die Einführung eines neuen Schlüsselworts in die Sprache minimiert, was unserer Ansicht nach für Benutzer mit einer bereits vorhandenen CodeBase besonders wichtig ist.  Gleichzeitig erhalten so Benutzer, die die neue Funktionalität einsetzen, ein erstklassiges Erlebnis des zusätzlichen Sprachfeatures, was in Managed Extensions nicht möglich war.  Ein Beispiel zur Verwendung von `sealed` finden Sie unter [Deklaration eines verwalteten Klassentyps](../dotnet/declaration-of-a-managed-class-type.md).  
  
 Ein durch Leerzeichen getrenntes Schlüsselwort wie z. B. `value class` stellt einen Sonderfall eines Kontextschlüsselworts dar.  Es bildet ein Paar aus einem vorhandenen Schlüsselwort und einem Kontextmodifizierer, die durch ein Leerzeichen getrennt sind.  Das Paar wird nicht wie zwei getrennte Schlüsselwörter, sondern als Einheit behandelt.  
  
## Siehe auch  
 [Einführung in die C\+\+\/CLI\-Migration](../dotnet/cpp-cli-migration-primer.md)   
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)