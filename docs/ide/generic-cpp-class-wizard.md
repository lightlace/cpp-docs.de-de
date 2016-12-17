---
title: "Generischer C++-Klassen-Assistent"
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
  - "vc.codewiz.class.generic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Generischer C++-Klassen-Assistent [C++]"
ms.assetid: aa95be9e-fc1b-45db-a11d-0d32c4929077
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Generischer C++-Klassen-Assistent
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fügt einem Projekt eine generische C\+\+\-Klasse hinzu.  Die Klasse erbt nicht von ATL oder MFC.  
  
 **Klassenname**  
 Legt den Namen der neuen Klasse fest.  
  
 **.h\-Datei**  
 Legt den Namen der Headerdatei für die neue Klasse fest.  Dieser Name basiert standardmäßig auf dem Namen, den Sie unter **Klassenname** angeben.  Klicken Sie auf die Schaltfläche mit den Auslassungspunkten \(**...**\), um die Headerdatei am gewünschten Speicherort zu speichern oder um die Klassendeklaration an eine vorhandene Datei anzufügen.  Wenn Sie eine vorhandene Datei angeben und dann auf **Fertig stellen** klicken, wird vom Assistenten eine Bestätigung angefordert, anzugeben, ob die Klassendeklaration an den Inhalt der Datei anzufügen ist.  Zum Anfügen an die Deklaration klicken Sie auf **Ja**, um die Datei anzufügen, und klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.  
  
 **.cpp\-Datei**  
 Legt den Namen der Implementierungsdatei für die neue Klasse fest.  Dieser Name basiert standardmäßig auf dem Namen, den Sie unter **Klassenname** angeben.  Klicken Sie auf die Schaltfläche mit den Auslassungspunkten \(**...**\), um die Implementierungsdatei am gewünschten Speicherort zu speichern oder um die Klassendefinition an eine vorhandene Datei anzufügen.  Wenn Sie eine vorhandene Datei angeben und dann auf **Fertig stellen** klicken, wird vom Assistenten eine Bestätigung angefordert, anzugeben, ob die Klassendefinition an den Inhalt der Datei anzufügen ist.  Zum Anfügen an die Definition klicken Sie auf **Ja**, um die Datei anzufügen, und klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.  
  
 **Basisklasse**  
 Legt die Basisklasse für die neue Klasse fest.  
  
 **Zugriff**  
 Legt für die neue Klasse den Zugriff auf die Basisklassenmember fest.  Zugriffsmodifizierer sind Schlüsselwörter, die festlegen, welche Zugriffsebene andere Klassen auf die Klassenmemberfunktion haben.  Weitere Informationen zum Angeben des Zugriffs finden Sie unter [Memberzugriffssteuerung](../cpp/member-access-control-cpp.md).  Standardmäßig ist die Klassenzugriffsebene auf `public` gesetzt.  
  
-   `public`  
  
-   `protected`  
  
-   `private`  
  
-   **Standard** \(Es wird kein Zugriffsmodifizierer generiert.\)  
  
 **Virtueller Destruktor**  
 Gibt an, ob der Klassendestruktor virtuell ist.  Mithilfe eines virtuellen Destruktors können Sie sicherstellen, dass der richtige Destruktor aufgerufen wird, wenn Instanzen abgeleiteter Klassen gelöscht werden.  
  
 **Inline**  
 Erstellt sowohl den Klassenkonstruktor als auch die Klassendefinition als Inlinefunktionen in der Headerdatei.  
  
 **Verwaltet**  
 Wenn diese Option ausgewählt wird, werden eine verwaltete Klasse und eine Headerdatei hinzugefügt.  Bei Deaktivierung werden eine systemeigene Klasse und eine Headerdatei hinzugefügt.  
  
## Siehe auch  
 [Hinzufügen einer generischen C\+\+\-Klasse](../ide/adding-a-generic-cpp-class.md)