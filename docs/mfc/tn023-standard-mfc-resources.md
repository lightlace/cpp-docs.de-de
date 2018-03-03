---
title: 'TN023: MFC-Standardressourcen | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.resources
dev_langs:
- C++
helpviewer_keywords:
- resources [MFC]
- TN023
- standard resources
ms.assetid: 60af8415-c576-4c2f-a711-ca5da0b9a1f2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6fded011fda52dfde46804b03699dc93469e5e32
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tn023-standard-mfc-resources"></a>TN023: MFC-Standardressourcen
In diesem Hinweis werden die standard-Ressourcen mit bereitgestellt und von der MFC-Bibliothek erforderlich.  
  
## <a name="standard-resources"></a>Standardressourcen  
 MFC bietet zwei Kategorien von vordefinierten Ressourcen, die Sie in Ihrer Anwendung verwenden können: ClipArt Ressourcen und standardframeworkressourcen.  
  
 ClipArt Ressourcen sind zusätzliche Ressourcen, die das Framework nicht abhängig, aber die Benutzeroberfläche Ihrer Anwendung hinzufügen möchten. Die folgenden ClipArt Ressourcen sind im allgemeinen MFC-Beispiel enthalten [CLIPART](../visual-cpp-samples.md):  
  
-   Common.rc: Eine einzelne Datei von Ressourcen mit:  
  
    -   Eine große Auflistung von Symbolen, die eine Vielzahl von geschäftlichen und Data-Verarbeitungsaufgaben darstellen.  
  
    -   Mehrere allgemeine Cursor (Siehe auch Afxres.rc).  
  
    -   Eine Bitmap für die Symbolleiste, die mehrere Symbolleistenschaltflächen enthält.  
  
    -   Die Bitmap und Symbol für Ressourcen, die von Commdlg.dll verwendet werden.  
  
-   Indicate.rc: Enthält die Zeichenfolgenressourcen für die Statusleiste Schlüssel-Status-Indikatoren, z. B. "Obergrenze" für die FESTSTELLTASTE aktiviert.  
  
-   Prompts.rc: Enthält das Menü eingabeaufforderungs-Zeichenfolgenressourcen für jeden Befehl, z. B. "Neues Dokument erstellen" für `ID_FILE_NEW`.  
  
-   COMMDLG.rc: Eine Visual C++ kompatibel RC-Datei, die die standardmäßigen COMMDLG Dialogfeldvorlagen enthält.  
  
 Standard Frameworkressourcen sind mit AFX definierte IDs, von denen das Framework für interne Implementierungen abhängig. Sie müssen nur selten diese AFX definierte Ressourcen zu ändern. Wenn Sie dies tun, sollten Sie das weiter unten in diesem Thema beschriebene Verfahren befolgen.  
  
 Die folgenden Frameworkressourcen sind im Verzeichnis MFC\INCLUDE enthalten:  
  
-   AFXRES.rc: Allgemeine Ressourcen vom Framework verwendet.  
  
-   Afxprint.rc: Spezielle Ressourcen für drucken.  
  
-   Afxolecl.rc: Spezielle Ressourcen für OLE-Clientanwendungen.  
  
-   Afxolev.rc: Spezielle Ressourcen für vollständige OLE-serveranwendungen.  
  
## <a name="using-clip-art-resources"></a>Verwenden von ClipArt Ressourcen  
  
#### <a name="to-use-a-clip-art-binary-resource"></a>Ein ClipArt Ressource "binary" verwendet  
  
1.  Öffnen Sie Ihre Anwendung Ressourcendatei in Visual C++.  
  
2.  Öffnen Sie Common.rc. Diese Datei enthält alle binären ClipArt-Ressourcen. Dies kann einige Zeit dauern, da die Common.rc-Datei kompiliert wird.  
  
3.  Halten Sie STRG GEDRÜCKT, und ziehen Sie die Ressourcen, die Sie aus Common.rc Ressourcendatei für Ihre Anwendung verwenden möchten.  
  
 Wenn andere ClipArt Ressourcen verwenden möchten, befolgen Sie dieselben Schritte aus. Der einzige Unterschied ist, dass Sie die entsprechenden RC-Datei anstelle von Common.rc geöffnet werden.  
  
> [!NOTE]
>  Achten Sie darauf, dass nicht auf Ressourcen außerhalb des gültigen Common.rc unbeabsichtigt dauerhaft zu verschieben. Wenn Sie die STRG-Taste halten, während Sie Ressourcen ziehen, erstellen Sie eine Kopie. Wenn Sie nicht STRG Sie beim Ziehen gedrückt werden, werden die Ressourcen verschoben. Wenn Sie Bedenken haben, dass Sie versehentlich Änderungen an der Datei Common.rc vorgenommen haben, möglicherweise, klicken Sie auf "Nein", wenn Sie gefragt werden, an, ob die Änderungen zu Common.rc gespeichert.  
  
> [!NOTE]
>  Die RC-Ressourcendateien haben eine spezielle `TEXTINCLUDE` Ressource darin, die Sie versehentlich zusätzlich zu den standardmäßigen RC-Dateien speichern verhindern.  
  
### <a name="customizing-standard-framework-resources"></a>Anpassen des Standard-Framework-Ressourcen  
 Standardframeworkressourcen Ressourcen werden in der Regel in einer Anwendung enthalten, mithilfe der #include Befehl in einer Anwendung Ressourcendatei. AppWizard wird eine Ressourcendatei zu generieren. Diese Datei enthält die entsprechenden standardframeworkressourcen-Ressourcen, je nachdem welche AppWizard-Optionen, die Sie auswählen. Sie können überprüfen, hinzufügen oder entfernen, welche Ressourcen durch Ändern der Kompilierzeitdirektiven enthalten sind. Öffnen Sie hierzu die **Ressource** Menü **Gruppe enthält**. Betrachten Sie das Element der "Kompilierzeitdirektiven" Bearbeiten. Zum Beispiel:  
  
```  
#include "afxres.rc"  
#include "afxprint.rc"  
```  
  
 Anpassen des standard-Framework-Ressourcen der häufigste Fall ist das Hinzufügen oder Entfernen von zusätzlichen enthält, für das Drucken OLE-Client und Unterstützung von OLE-Server.  
  
 In einigen seltenen Fällen, die Sie möglicherweise den Inhalt der standardframeworkressourcen Ressourcen für eine bestimmte Anwendung anpassen möchten, nicht einfach fügen Sie hinzu und entfernen Sie die gesamte Datei. Die folgenden Schritte zeigen, wie Sie die Ressourcen beschränken können, die enthalten sind:  
  
##### <a name="to-customize-the-contents-of-a-standard-resource-file"></a>Der Inhalt einer standard-Ressourcendatei angepasst  
  
1.  Öffnen Sie die Ressourcendatei in Visual C++.  
  
2.  Entfernen Sie mithilfe des Befehls Ressourcenincludes legen die `#include` für die standard-RC-Datei, die Sie anpassen möchten. Entfernen Sie z. B. zum Anpassen der Seitenansicht-Symbolleiste die `#include "afxprint.rc"` Zeile.  
  
3.  Öffnen Sie die entsprechenden standard Ressourcendateien in MFC\INCLUDE. Das Beispiel weiter oben in diesem Thema wird die entsprechende Datei MFC\Include\Aafxprint.rc  
  
4.  Kopieren Sie alle Ressourcen aus der standardmäßigen RC-Datei zu Ihrer Ressourcendatei für die Anwendung.  
  
5.  Ändern Sie die Kopie die standard-Ressourcen in Ihrer Anwendungsressourcendatei.  
  
> [!NOTE]
>  Ändern Sie die Ressourcen direkt in der standardmäßigen RC-Dateien nicht. Auf diese Weise ändern sich die Ressourcen in jeder Anwendung, nicht nur an, die Sie gerade arbeiten.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

