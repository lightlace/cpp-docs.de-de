---
title: Generischer C++-Klassen-Assistent | Microsoft Docs
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
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="generic-c-class-wizard"></a>Generischer C++-Klassen-Assistent
Ein Projekt hinzugefügt eine generische C++-Klasse. Die Klasse erbt nicht von ATL bzw. MFC.  
  
 **Klassenname**  
 Legt den Namen der neuen Klasse.  
  
 **.h-Datei**  
 Legt den Namen der Headerdatei für die neue Klasse. Standardmäßig basiert auf den Namen, die Sie, in angeben diesen Namen **Klassenname**. Die Header-Datei auf den Speicherort Ihrer Wahl speichern oder die Klassendeklaration an eine vorhandene Datei angefügt werden soll, klicken Sie auf die Schaltfläche mit den Auslassungspunkten (**...** ). Wenn Sie eine vorhandene Datei angeben, wenn Sie auf **Fertig stellen**, der Assistent fordert Sie angeben, ob die Klassendeklaration an den Inhalt der Datei angefügt werden sollen. Um die Deklaration anzufügen, klicken Sie auf **Ja**; um zum Assistenten zurückzukehren, geben Sie einen anderen Dateinamen an, und klicken Sie auf **keine**.  
  
 **CPP-Datei**  
 Legt den Namen der Implementierungsdatei für die neue Klasse. Standardmäßig basiert auf den Namen, die Sie, in angeben diesen Namen **Klassenname**. Die Implementierungsdatei am Speicherort Ihrer Wahl speichern oder die Definition der Klasse an eine vorhandene Datei angefügt werden soll, klicken Sie auf die Schaltfläche mit den Auslassungspunkten (**...** ). Wenn Sie eine vorhandene Datei angeben, wenn Sie auf **Fertig stellen**, der Assistent fordert Sie angeben, ob die Klassendefinition auf den Inhalt der Datei angefügt werden sollen. Um die Definition anzufügen, klicken Sie auf **Ja**; um zum Assistenten zurückzukehren, geben Sie einen anderen Dateinamen an, und klicken Sie auf **keine**.  
  
 **Basisklasse**  
 Legt die Basisklasse für die neue Klasse an.  
  
 **Zugriff**  
 Legt den Zugriff auf die Member der Basisklasse für die neue Klasse. Zugriffsmodifizierer sind Schlüsselwörter, die die Zugriffsebene angeben, die andere Klassen mit Memberfunktionen der Klasse haben. Weitere Informationen über das Angeben von Access finden Sie unter [Memberzugriffssteuerung](../cpp/member-access-control-cpp.md). Standardmäßig Zugriff auf Klassenebene festgelegt ist, um `public`.  
  
-   `public`  
  
-   `protected`  
  
-   `private`  
  
-   **Standard** (es ist keine Zugriffsmodifizierer generiert.)  
  
 **Virtuellen Destruktor**  
 Gibt an, ob der Klassendestruktor virtuell ist. Verwenden eines virtuellen Destruktors trägt dazu bei, dass der richtige Destruktor aufgerufen wird, wenn Instanzen von abgeleiteten Klassen gelöscht werden.  
  
 **Inline**  
 Generiert den Klassenkonstruktor und der Klassendefinition als Inlinefunktionen in der Headerdatei.  
  
 **Verwaltet**  
 Bei Auswahl dieser Option fügt eine verwaltete Klasse und Header-Datei hinzu. Wenn diese Option deaktiviert ist, wird eine systemeigene Klasse und Header-Datei hinzugefügt.  
  
## <a name="see-also"></a>Siehe auch  
 [Hinzufügen einer generischen C++-Klasse](../ide/adding-a-generic-cpp-class.md)