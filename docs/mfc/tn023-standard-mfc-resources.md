---
title: 'TN023: MFC-Standardressourcen'
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.resources
helpviewer_keywords:
- resources [MFC]
- TN023
- standard resources
ms.assetid: 60af8415-c576-4c2f-a711-ca5da0b9a1f2
ms.openlocfilehash: 04789ba85a9f7c193a88ba1a0d097b3671808e9b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50559912"
---
# <a name="tn023-standard-mfc-resources"></a>TN023: MFC-Standardressourcen

In diesem Hinweis wird beschrieben, die standard-Ressourcen mit bereitgestellt und wird von der MFC-Bibliothek benötigt wird.

## <a name="standard-resources"></a>Standard-Ressourcen

MFC bietet zwei Kategorien von vordefinierten Ressourcen, die Sie in Ihrer Anwendung verwenden können: ClipArt-Ressourcen und standard-Framework.

ClipArt-Ressourcen sind zusätzliche Ressourcen, die das Framework nicht abhängig ist, aber die Benutzeroberfläche Ihrer Anwendung hinzufügen möchten. Die folgenden ClipArt-Ressourcen befinden sich im allgemeinen MFC-Beispiel [CLIPART](../visual-cpp-samples.md):

- Common.rc: Eine einzelne Datei von Ressourcen mit:

   - Eine umfangreiche Auflistung von Symbolen, die eine Vielzahl von Unternehmen und Aufgaben der Datenverarbeitung darstellen.

   - Einige allgemeine Cursor (Siehe auch Afxres.rc).

   - Eine Bitmap für die Symbolleiste, die mehrere Symbolleisten-Schaltflächen enthält.

   - Die Bitmap und Symbol für Ressourcen, die von Commdlg.dll verwendet werden.

- Indicate.rc: Enthält die Zeichenfolgenressourcen für die Statusleiste-Key-Status-Indikatoren, z. B. "Obergrenze" für die FESTSTELLTASTE aktiviert.

- Prompts.rc: Enthält die Menü-Eingabeaufforderung Zeichenfolgenressourcen für jeden vordefinierten Befehl ein, z. B. "Neues Dokument erstellen" für ID_FILE_NEW.

- COMMDLG.rc: Einer Visual C++ kompatibel RC-Datei, die die standardmäßige COMMDLG Dialogfeldvorlagen enthält.

Standard Frameworkressourcen sind Ressourcen mit AFX definierte-IDs, von denen das Framework für die interne Implementierungen abhängig. Sie müssen nur selten diese AFX definierte Ressourcen zu ändern. Wenn Sie dies tun, sollten Sie das weiter unten in diesem Thema beschriebenen Verfahren befolgen.

Die folgenden Frameworkressourcen sind im Verzeichnis MFC\INCLUDE enthalten:

- AFXRES.rc: Allgemeine Ressourcen vom Framework verwendet.

- Afxprint.rc: Spezielle Ressourcen für drucken.

- Afxolecl.rc: Spezielle Ressourcen für OLE-Client-Anwendungen.

- Afxolev.rc: Spezielle Ressourcen für vollständige OLE-serveranwendungen.

## <a name="using-clip-art-resources"></a>ClipArt-Ressourcen

#### <a name="to-use-a-clip-art-binary-resource"></a>Eine binäre Ressourcendatei mit ClipArt-Verwendung

1. Öffnen Sie in Visual C++ Ressourcendatei der Anwendung ein.

1. Öffnen Sie Common.rc. Diese Datei enthält alle binären ClipArt-Ressourcen. Dies kann einige Zeit dauern, da die Common.rc-Datei kompiliert wird.

1. Halten Sie STRG GEDRÜCKT, und ziehen Sie die Ressourcen, die Sie vom Common.rc an Ressourcendatei der Anwendung verwenden möchten.

Um andere ClipArt-Ressourcen zu verwenden, führen Sie die gleichen Schritte aus. Der einzige besteht Unterschied darin, dass Sie die entsprechenden RC-Datei anstelle von Common.rc geöffnet werden.

> [!NOTE]
>  Achten Sie darauf, dass Sie nicht versehentlich Ressourcen aus Common.rc dauerhaft verschieben. Wenn Sie die STRG-Taste enthalten, und ziehen Sie die Ressourcen, erstellen Sie eine Kopie. Wenn Sie nicht STRG halten Sie beim Ziehen, werden die Ressourcen verschoben werden. Wenn Sie befürchten, dass Sie versehentlich die Common.rc-Datei geändert haben können, klicken Sie auf "Nein", wenn Sie gefragt werden, an, ob die Änderungen an Common.rc speichern.

> [!NOTE]
>  Die RC-Ressourcendateien enthalten eine besondere TEXTINCLUDE-Ressource, die Sie versehentlich auf standard RC-Dateien speichern verhindern.

### <a name="customizing-standard-framework-resources"></a>Anpassen des Standard-Framework-Ressourcen

Standard-Framework-Ressourcen in der Regel befinden sich in einer Anwendung mithilfe der #include Befehl in einer Anwendung Ressourcendatei. AppWizard wird eine Ressourcendatei zu generieren. Diese Datei enthält die richtige standard-Framework-Ressourcen, je nachdem welche AppWizard, die Optionen Sie auswählen. Sie können überprüfen, hinzufügen oder entfernen, welche Ressourcen durch Ändern der Kompilierzeitdirektiven enthalten sind. Zu diesem Zweck öffnen Sie die **Ressource** Menü **Gruppe enthält**. Sehen Sie sich das Element "Kompilierzeitdirektiven" Bearbeiten. Zum Beispiel:

```
#include "afxres.rc"
#include "afxprint.rc"
```

Der häufigste Fall Anpassen des standard-Framework-Ressourcen ist das Hinzufügen oder Entfernen von zusätzlichen enthält, für den Druck, OLE-Client und OLE-serverunterstützung.

In einigen seltenen Fällen kann der Inhalt der standard-Framework-Ressourcen für Ihre spezifische Anwendung angepasst werden sollen, nicht nur fügen Sie hinzu und entfernen Sie die gesamte Datei. Die folgenden Schritte zeigen, wie Sie die Ressourcen beschränken können, die enthalten sind:

##### <a name="to-customize-the-contents-of-a-standard-resource-file"></a>Anpassung der Inhalte einer Datei für die standard-Ressource

1. Öffnen Sie die Ressourcendatei in Visual C++.

1. Mit dem Befehl Ressourcenincludes festlegen, entfernen Sie die `#include` für die standard-RC-Datei, die Sie anpassen möchten. Entfernen Sie z. B. zum Anpassen der Seitenansicht-Symbolleiste die `#include "afxprint.rc"` Zeile.

1. Öffnen Sie die entsprechenden standard-Ressourcen-Dateien in MFC\INCLUDE an. Nach dem Beispiel oben in diesem Thema wird die entsprechende Datei MFC\Include\Aafxprint.rc

1. Kopieren Sie alle Ressourcen aus der standard-RC-Datei Ihrer Ressourcendatei der Anwendung ein.

1. Ändern Sie die Kopie der standard-Ressourcen in Ihrer Ressourcendatei der Anwendung.

> [!NOTE]
>  Ändern Sie die Ressourcen direkt in der standard-RC-Dateien nicht. Auf diese Weise ändern sich die Ressourcen verfügbar sind, in jeder Anwendung, nicht nur im diejenige aus, die Sie gerade arbeiten.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

