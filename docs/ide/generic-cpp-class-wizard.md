---
title: Generischer C++-Klassen-Assistent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.class.generic
dev_langs:
- C++
helpviewer_keywords:
- Generic C++ Class Wizard [C++]
ms.assetid: aa95be9e-fc1b-45db-a11d-0d32c4929077
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43e86a4047ef025f49dd01eda90f324623a90752
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33328304"
---
# <a name="generic-c-class-wizard"></a>Generischer C++-Klassen-Assistent
Fügt einem Projekt eine generische C++-Klasse hinzu. Die Klasse erbt nicht von ATL oder MFC.  
  
 **Klassenname**  
 Legt den Namen der neuen Klasse fest.  
  
 **H-Datei**  
 Legt den Namen der Headerdatei für die neue Klasse fest. Standardmäßig basiert dieser Name auf dem Namen, den Sie unter **Klassenname** angeben. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten (**...**), um die Headerdatei am gewünschten Speicherort zu speichern oder um die Klassendeklaration an eine vorhandene Datei anzufügen. Wenn Sie eine vorhandene Datei angeben, fordert der Assistent Sie dazu auf, anzugeben, ob die Klassendeklaration an die Inhalte der Datei angefügt werden sollen, wenn Sie auf **Fertig stellen** klicken. Klicken Sie auf **Ja**, um die Deklaration anzufügen. Klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.  
  
 **CPP-Datei**  
 Legt den Namen der Implementierungsdatei für die neue Klasse fest. Standardmäßig basiert dieser Name auf dem Namen, den Sie unter **Klassenname** angeben. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten (**...**), um die Implementierungsdatei am gewünschten Speicherort zu speichern oder um die Klassendefinition an eine vorhandene Datei anzufügen. Wenn Sie eine vorhandene Datei angeben, fordert der Assistent Sie dazu auf, anzugeben, ob die Klassendefinition an die Inhalte der Datei angefügt werden sollen, wenn Sie auf **Fertig stellen** klicken. Klicken Sie auf **Ja**, um die Definition anzufügen. Klicken Sie auf **Nein**, um zum Assistenten zurückzukehren und einen anderen Dateinamen anzugeben.  
  
 **Basisklasse**  
 Legt die Basisklasse für die neue Klasse fest.  
  
 **Zugriff**  
 Legt den Zugriff auf die Member der Basisklasse für die neue Klasse fest. Bei Zugriffsmodifizierern handelt es sich um Schlüsselwörter, die den Zugriff festlegen, den andere Klassen auf die Klassenmemberfunktionen haben. Weitere Informationen zum Angeben des Zugriffs finden Sie unter [Member Access Control (Memberzugriffssteuerung)](../cpp/member-access-control-cpp.md). Der Klassenzugriff ist standardmäßig auf `public` festgelegt.  
  
-   `public`  
  
-   `protected`  
  
-   `private`  
  
-   **Standard** (kein Zugriffsmodifizierer wird generiert)  
  
 **Virtueller Destruktor**  
 Gibt an, ob der Klassendestruktor virtuell ist. Die Verwendung eines virtuellen Destruktors trägt dazu bei, sicherzustellen, dass der richtige Destruktor aufgerufen wird, wenn Instanzen abgeleiteter Klassen gelöscht werden.  
  
 **Inline**  
 Generiert sowohl den Klassenkonstruktor als auch die Klassendefinition als Inlinefunktionen in der Headerdatei.  
  
 **Verwaltet**  
 Wenn diese Option ausgewählt ist, werden eine verwaltete Klasse und Headerdatei hinzugefügt. Wenn diese Option nicht ausgewählt ist, werden eine native Klasse und Headerdatei hinzugefügt.  
  
## <a name="see-also"></a>Siehe auch  
 [Hinzufügen einer generischen C++-Klasse](../ide/adding-a-generic-cpp-class.md)