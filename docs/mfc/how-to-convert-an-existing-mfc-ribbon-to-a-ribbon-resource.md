---
title: 'Vorgehensweise: Konvertieren ein vorhandenes MFC-Menübands in eine Menübandressource | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ribbon resource, converting from an MFC ribbon
- MFC ribbon, converting to a ribbon resource
ms.assetid: 324b7ff6-58f9-4691-96a9-9836a79d0fb6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8024acc4abbb02b14ed968df83779d34bd4a7271
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351649"
---
# <a name="how-to-convert-an-existing-mfc-ribbon-to-a-ribbon-resource"></a>Gewusst wie: Umwandeln eines vorhandenen MFC-Menübands in eine Menübandressource
Menübandressourcen sind einfacher zu visualisieren, ändern und als manuell codierten Menübänder verwalten. In diesem Thema wird beschrieben, wie ein manuell codiertes Menüband in einem MFC-Projekt in eine menübandressource konvertieren.  
  
 Benötigen Sie ein vorhandenes MFC-Projekt mit Code, der die MFC-Menübandklassen, z. B. verwendet [CMFCRibbonBar Class](../mfc/reference/cmfcribbonbar-class.md).  
  
### <a name="to-convert-an-mfc-ribbon-to-a-ribbon-resource"></a>Eine MFC-Menübands in eine menübandressource konvertieren  
  
1.  Öffnen Sie in Visual Studio in einem vorhandenen MFC-Projekt die Quelldatei, in dem das Objekt CMFCRibbonBar initialisiert wird. In der Regel ist die Datei "MainFrm.cpp". Fügen Sie den folgenden Code nach der Initialisierungscode für das Menüband aus.  
  
 ```  
    m_wndRibbonBar.SaveToXMLFile("RibbonOutput.xml");

 ```  
  
     Speichern und schließen Sie die Datei.  
  
2.  Erstellen Sie und führen Sie die MFC-Anwendung, öffnen Sie im Editor RibbonOutput.txt, und kopieren Sie den Inhalt.  
  
3.  In Visual Studio auf die **Projekt** Menü klicken Sie auf **Ressource hinzufügen**. In der **Ressource hinzufügen** wählen Sie im Dialogfeld **Menüband** , und klicken Sie dann auf **neu**.  
  
     Visual Studio erstellt eine menübandressource und öffnet sie in der Entwurfsansicht. Das Menübandressourcen-ID lautet IDR_RIBBON1 und in angezeigt wird **Ressourcenansicht**. Das Menüband ist in der ribbon1.mfcribbon-ms-XML-Datei definiert.  
  
4.  Öffnen Sie in Visual Studio ribbon1.mfcribbon ms, löschen Sie den Dateiinhalt und fügen Sie den Inhalt der RibbonOutput.txt, die Sie zuvor kopiert haben. Speichern Sie und schließen Sie ribbon1.mfcribbon ms.  
  
5.  Öffnen Sie erneut die Quelldatei, in dem das CMFCRibbonBar Objekt initialisiert wird (in der Regel "MainFrm.cpp") und kommentieren Sie den vorhandenen Code im Menüband. Fügen Sie den folgenden Code nach dem Code, dem Sie auskommentiert.  
  
 ```  
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);

 ```  
  
6.  Erstellen Sie das Projekt, und führen Sie das Programm.  
  
## <a name="see-also"></a>Siehe auch  
 [Menüband-Designer (MFC)](../mfc/ribbon-designer-mfc.md)

