---
title: Verwalten von Daten mit Dokumentdatenvariablen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- documents [MFC], data storage
- friend classes [MFC]
- classes [MFC], friend
- data [MFC]
- data [MFC], documents
- collection classes [MFC], used by document object
- document data [MFC]
- member variables [MFC], document class [MFC]
ms.assetid: e70b87f4-8c30-49e5-8986-521c2ff91704
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c737557d503ca7e0959d159a0818f1ca78280ea2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="managing-data-with-document-data-variables"></a>Verwalten von Daten mit Dokumentdatenvariablen
Implementieren Sie die Daten des Dokuments als Membervariablen der Dokumentklasse. Das Scribble-Programm deklariert beispielsweise einen Datenmember des Typs `CObList` – eine verknüpfte Liste, die Zeiger auf speichert `CObject` Objekte. Diese Liste wird verwendet, um Arrays von Punkten zu speichern, aus denen eine Freihandlinie Strichzeichnung besteht.  
  
 Wie Sie Ihr Dokument Elementdaten implementieren, hängt von der Art der Anwendung ab. Zum einfacheren out MFC bietet eine Gruppe von "Auflistungsklassen" – Arrays, Listen und Zuordnungen (Wörterbücher), einschließlich Sammlungen, die basierend auf C++-Vorlagen – zusammen mit den Klassen, die eine Vielzahl von gängigen Datentypen wie z. B. kapseln `CString`, `CRect`, `CPoint`, `CSize`, und `CTime`. Weitere Informationen zu diesen Klassen finden Sie unter der [Class Library Overview](../mfc/class-library-overview.md) in der *MFC-Referenz*.  
  
 Wenn Sie Ihr Dokument Elementdaten definieren, fügen in der Regel Sie Memberfunktionen der Dokument-Klasse zum Festlegen und Abrufen von Datenelementen und andere nützliche Vorgänge darauf.  
  
 Die Sicht Zeiger auf das Dokument, in der Sicht zum Zeitpunkt der Erstellung installiert über Ihre Ansichten sind das Document-Objekt zugreifen. Sie können die this-Zeiger in eine Sicht Memberfunktionen abrufen, durch Aufrufen der `CView` Memberfunktion **GetDocument**. Achten Sie darauf, dass Sie für Ihre eigenen Dokumenttyp this-Zeiger umgewandelt. Dann können Sie Mitglieder für Öffentliche Dokumente über den Zeiger zugreifen.  
  
 Wenn häufige Datenübertragung Direktzugriff erfordert, oder Sie nicht öffentliche Member der Dokumentklasse verwenden möchten, empfiehlt es sich, die Ihrer Ansicht einen "Friend" (in der C++-Terminologie) der Dokumentklasse Klasse sein.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Dokumenten](../mfc/using-documents.md)

