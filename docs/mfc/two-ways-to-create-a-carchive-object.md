---
title: "Zwei Möglichkeiten zum Erstellen eines CArchive-Objekts | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CArchive
dev_langs:
- C++
helpviewer_keywords:
- CArchive class [MFC], closing CArchive objects
- CArchive objects [MFC], closing
- I/O [MFC], creating CArchive objects
- serialization [MFC], CArchive class
- CArchive objects [MFC]
- storage [MFC], CArchive class [MFC]
- data storage [MFC], CArchive class
- CArchive class [MFC], constructor
ms.assetid: aefa28ce-b55c-40dc-9e42-5f038030985d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1b1db549544d421600ed6dae1a8a987006c2ab6c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="two-ways-to-create-a-carchive-object"></a>Zwei Möglichkeiten zur Erstellung eines CArchive-Objekts
Es gibt zwei Möglichkeiten zum Erstellen einer `CArchive` Objekt:  
  
-   [Implizite Erstellung eines CArchive-Objekts über das framework](#_core_implicit_creation_of_a_carchive_object_via_the_framework)  
  
-   [Explizite Erstellung eines CArchive-Objekts](#_core_explicit_creation_of_a_carchive_object)  
  
##  <a name="_core_implicit_creation_of_a_carchive_object_via_the_framework"></a>Implizite Erstellung eines CArchive-Objekts über das Framework  
 Die gängigste und einfachste, Methode ist, lassen das Framework erstellen eine `CArchive` Objekt für das Dokument im Auftrag der speichern, speichern und Befehlen im Menü Datei öffnen.  
  
 Hier ist, was das Framework ermöglicht, wenn der Benutzer der Anwendung den Befehl "Speichern unter" über das Menü Datei ausgibt:  
  
1.  Zeigt die **speichern unter** (Dialogfeld) und ruft den Dateinamen des Benutzers ab.  
  
2.  Öffnet die Datei mit dem Namen vom Benutzer als ein `CFile` Objekt.  
  
3.  Erstellt eine `CArchive` -Objekt, das auf diese verweist `CFile` Objekt. Bei der Erstellung der `CArchive` -Objekt, das Framework wird der Modus auf "Speichern" (schreiben, serialisieren), im Gegensatz zu "laden" (Lesen, deserialisieren).  
  
4.  Ruft die `Serialize` in definierte Funktion Ihrer **CDocument**-abgeleitete Klasse, und übergeben sie einen Verweis auf die `CArchive` Objekt.  
  
 Ihr Dokuments `Serialize` Funktion schreibt dann die Daten in der `CArchive` -Objekts, wie in Kürze erläutert. Bei der Rückgabe aus Ihrer `Serialize` -Funktion, die das Framework zerstört die `CArchive` Objekt und dann die `CFile` Objekt.  
  
 Daher, wenn Sie das Framework erstellen können die `CArchive` -Objekt für das Dokument ist müssen Sie lediglich des Dokuments implementieren `Serialize` -Funktion, die Schreibvorgänge und verschiedene andere und aus dem Archiv gelesen. Außerdem müssen Sie implementieren `Serialize` für eine beliebige `CObject`-abgeleitete Objekte, die des Dokuments `Serialize` Funktion wiederum serialisiert, direkt oder indirekt.  
  
##  <a name="_core_explicit_creation_of_a_carchive_object"></a>Explizite Erstellung eines CArchive-Objekts  
 Neben dem Serialisieren eines Dokuments über das Framework, stehen die anderen Fällen müssen Sie die möglicherweise eine `CArchive` Objekt. Angenommen, Sie möchten möglicherweise Serialisieren von Daten in und aus der Zwischenablage, dargestellt durch eine `CSharedFile` Objekt. Oder Sie möchten verwenden eine Benutzeroberfläche zum Speichern einer Datei, die andere als die vom Framework bereitgestellt wird. In diesem Fall können Sie explizit erstellen eine `CArchive` Objekt. Sie dazu die gleiche Weise wie, die das Framework ermöglicht, die mithilfe des folgenden Verfahrens.  
  
#### <a name="to-explicitly-create-a-carchive-object"></a>Ein CArchive-Objekt explizit zu erstellen.  
  
1.  Erstellen einer `CFile` Objekt oder ein Objekt abgeleitet `CFile`.  
  
2.  Übergeben Sie die `CFile` Objekt an den Konstruktor für `CArchive`, wie im folgenden Beispiel gezeigt:  
  
     [!code-cpp[NVC_MFCSerialization#5](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_1.cpp)]  
  
     Das zweite Argument der `CArchive` Konstruktor ist ein Enumerationswert, der angibt, ob das Archiv für das Speichern oder Laden von Daten an ein oder aus der Datei verwendet wird. Die `Serialize` Funktion eines Objekts überprüft dieser Status durch Aufrufen der `IsStoring` Funktion für das Archivobjekt.  
  
 Sie abschließend speichern oder Laden von Daten an ein oder aus der `CArchive` -Objekt, schließen Sie es. Obwohl die `CArchive` (und `CFile`) Objekte werden automatisch geschlossen, das Archiv (und die Datei), es wird empfohlen, die explizit dazu seit der Wiederherstellung nach Fehlern erleichtert. Weitere Informationen zur Fehlerbehandlung finden Sie im Artikel [Ausnahmen: Abfangen und Löschen von Ausnahmen](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
#### <a name="to-close-the-carchive-object"></a>Schließen des CArchive-Objekt  
  
1.  Im folgende Beispiel wird veranschaulicht, wie schließen die `CArchive` Objekt:  
  
     [!code-cpp[NVC_MFCSerialization#6](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_2.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Serialisierung: Serialisieren eines Objekts](../mfc/serialization-serializing-an-object.md)

