---
title: 'Gewusst wie: Umwandeln eines vorhandenen MFC-Menübands in eine Menübandressource'
ms.date: 11/04/2016
helpviewer_keywords:
- ribbon resource, converting from an MFC ribbon
- MFC ribbon, converting to a ribbon resource
ms.assetid: 324b7ff6-58f9-4691-96a9-9836a79d0fb6
ms.openlocfilehash: 627c50758b10ad18e45fc1432340c0eb2dad7b19
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51524351"
---
# <a name="how-to-convert-an-existing-mfc-ribbon-to-a-ribbon-resource"></a>Gewusst wie: Umwandeln eines vorhandenen MFC-Menübands in eine Menübandressource

Menübandressourcen sind leichter zu visualisieren, ändern und als manuell codiertes Menübänder verwalten. In diesem Thema wird beschrieben, wie Sie ein manuell codiertes Menüband in einem MFC-Projekt in eine menübandressource konvertieren.

Benötigen Sie ein vorhandenes MFC-Projekt mit Code, der die MFC-Menübandklassen, z. B. verwendet [CMFCRibbonBar Class](../mfc/reference/cmfcribbonbar-class.md).

### <a name="to-convert-an-mfc-ribbon-to-a-ribbon-resource"></a>Konvertieren ein MFC-Menübands in eine menübandressource

1. Öffnen Sie in Visual Studio in einem vorhandenen MFC-Projekt, auf die Registerkarte die Quelldatei, in denen die `CMFCRibbonBar` -Objekt initialisiert wird. In der Regel ist die Datei "MainFrm.cpp". Fügen Sie den folgenden Code nach dem Initialisierungscode für das Menüband aus.

```
    m_wndRibbonBar.SaveToXMLFile("RibbonOutput.xml");
```

   Speichern und schließen Sie die Datei.

1. Erstellen Sie und führen Sie die MFC-Anwendung, und klicken Sie dann öffnen Sie im Editor RibbonOutput.txt und kopieren Sie den Inhalt.

1. In Visual Studio auf die **Projekt** Menü klicken Sie auf **Ressource hinzufügen**. In der **Ressource hinzufügen** wählen Sie im Dialogfeld **Menüband** , und klicken Sie dann auf **neu**.

   Visual Studio erstellt eine menübandressource und öffnet sie in der Entwurfsansicht. Das Menübandressourcen-ID lautet IDR_RIBBON1 und in angezeigt wird **Ressourcenansicht**. Das Menüband ist in der ribbon1.mfcribbon-ms-XML-Datei definiert.

1. Klicken Sie in Visual Studio öffnen Sie ribbon1.mfcribbon-ms, löschen Sie den Dateiinhalt, und fügen Sie den Inhalt der RibbonOutput.txt, die Sie zuvor kopiert haben. Speichern Sie und schließen Sie ribbon1.mfcribbon ms.

1. Erneut öffnen die Quelldatei, in dem das CMFCRibbonBar-Objekt initialisiert wird (in der Regel "MainFrm.cpp"), und kommentieren Sie die vorhandene Multifunktionsleisten-Code. Fügen Sie den folgenden Code nach dem Code, dem Sie auskommentiert.

```
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);
```

1. Erstellen Sie das Projekt, und führen Sie das Programm.

## <a name="see-also"></a>Siehe auch

[Menüband-Designer (MFC)](../mfc/ribbon-designer-mfc.md)

