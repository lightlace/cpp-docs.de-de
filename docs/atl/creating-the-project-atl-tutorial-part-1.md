---
title: Erstellen des Projekts (ATL-Lernprogramm, Teil 1) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
ms.assetid: f6b727d1-390a-4b27-b82f-daadcd9fc059
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2d10aa6a3f7220103ae6a3b9e57b9b3c42cd8739
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="creating-the-project-atl-tutorial-part-1"></a>Erstellen des Projekts (ATL-Lernprogramm, Teil 1)
Dieses Lernprogramm führt Sie schrittweise durch ein nicht attributierte ATL-Projekt, das ein ActiveX-Objekt erstellt, die ein Polygon anzeigt. Das Objekt enthält die Optionen für der Benutzer so ändern Sie die Anzahl der Seiten, aus denen die Polygon und den Code um die Anzeige zu aktualisieren.  
  
> [!NOTE]
>  ATL und MFC werden in den Express-Editionen von Visual Studio in der Regel nicht unterstützt.  
  
> [!NOTE]
>  In diesem Lernprogramm erstellt den gleichen Quellcode als Polygon-Beispiel. Wenn Sie vermeiden, den Quellcode manuell eingeben möchten, können Sie laden Sie es der [Polygon-Beispiel](../visual-cpp-samples.md). Sie können dann auf den Quellcode Polygon verweisen, wie Sie das Lernprogramm zu absolvieren, oder Suchen nach Fehlern in Ihrem Projekt verwenden.  
  
### <a name="to-create-the-initial-atl-project-using-the-atl-project-wizard"></a>So erstellen das ursprüngliche ATL-Projekt mit dem ATL-Projekt-Assistenten  
  
1.  Klicken Sie in der Visual Studio-Entwicklungsumgebung auf **neu** auf die **Datei** Menü, und klicken Sie dann auf **Projekt**.  
  
2.  Klicken Sie auf die **Visual C++-Projekte** Ordner, und wählen **ATL-Projekt**.  
  
3.  Typ `Polygon` als Projektname verwendet.  
  
     Der Speicherort für den Quellcode wird in der Regel Eigene Dateien\Visual Studio-Projekte standardmäßig, und ein neuer Ordner wird automatisch erstellt werden.  
  
4.  Klicken Sie auf **OK** und der ATL-Projekt-Assistent wird geöffnet.  
  
5.  Klicken Sie auf **Anwendungseinstellungen** um die verfügbaren Optionen anzuzeigen.  
  
6.  Lassen Sie ein Steuerelement erstellen, und ein Steuerelement muss in-Process-Server sein, die **Anwendungstyp** als DLL.  
  
7.  Behalten Sie die anderen Optionen für die Standardwerte, und klicken Sie auf **Fertig stellen**.  
  
 ATL-Projektassistenten erstellen das Projekt, indem Sie mehrere Dateien zu generieren. Sie können diese Dateien im Projektmappen-Explorer anzeigen, indem Sie das Objekt Polygon erweitern. Die Dateien sind unten aufgeführt.  
  
|Datei|Beschreibung|  
|----------|-----------------|  
|Polygon.cpp hinzu|Enthält die Implementierung von `DllMain`, `DllCanUnloadNow`, `DllGetClassObject`, `DllRegisterServer`, und `DllUnregisterServer`. Außerdem enthält der objektzuordnung, dies ist eine Liste der ATL-Objekte in Ihrem Projekt ein. Dieser Wert ist zunächst leer.|  
|Polygon.def|Diese Moduldefinitionsdatei enthält den Linker mit Informationen über die Exporte, die die DLL erforderlich sind.|  
|Polygon.idl|Die IDL-Datei, die die Schnittstellen, die spezifisch für die Objekte beschreibt.|  
|Polygon.RGS|Diese Registrierungsskript enthält Informationen zum Registrieren Ihres Programms DLL.|  
|Polygon.rc|Die Ressourcendatei, die ursprünglich die Versionsinformationen und eine Zeichenfolge, enthält den Namen des Projekts enthält.|  
|Resource.h|Die Headerdatei für die Ressourcendatei.|  
|Polygonps.def|Diese Moduldefinitionsdatei enthält den Linker mit Informationen über die Exporte erforderlich, die für den Proxy und Stub-Code, der apartmentübergreifende Aufrufe unterstützt.|  
|stdafx.cpp|Die Datei, `#include` die Dateien der ATL-Implementierung.|  
|stdafx.h|Die Datei, `#include` die ATL-Headerdateien.|  
  
1.  Klicken Sie im Projektmappen-Explorer mit der Maustaste das `Polygon` Projekt.  
  
2.  Klicken Sie im Kontextmenü auf **Eigenschaften**.  
  
3.  Klicken Sie auf **Linker**. Ändern der **pro UserRedirection** option **Ja**.  
  
4.  Klicken Sie auf **OK**.  
  
 Im nächsten Schritt fügen Sie ein Steuerelement zu Ihrem Projekt hinzu.  
  
 [Schritt 2](../atl/adding-a-control-atl-tutorial-part-2.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Lernprogramm](../atl/active-template-library-atl-tutorial.md)

