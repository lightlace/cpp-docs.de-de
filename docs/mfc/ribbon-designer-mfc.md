---
title: Menüband-Designer (MFC)
ms.date: 11/19/2018
f1_keywords:
- vc.editors.ribbon.F1
helpviewer_keywords:
- Ribbon Designer (MFC)
- MFC Ribbon Designer
ms.assetid: 0806dfd6-7d11-471a-99e1-4072852231f9
ms.openlocfilehash: a39a3a69b43eb06d67fc806e2d4fa9aec323b650
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907819"
---
# <a name="ribbon-designer-mfc"></a>Menüband-Designer (MFC)

Mit dem Menüband-Designer können Sie Menübänder in MFC-Anwendungen erstellen und anpassen. Ein Menüband ist ein Element der Benutzeroberfläche (UI), auf dem Befehle in logischen Gruppen organisiert werden. Diese Gruppen werden auf separaten Registerkarten in einem Streifen entlang des oberen Fensterrahmens angezeigt. Das Menüband ersetzt die Menü- und Symbolleisten. Mit einem Menüband kann die Benutzerfreundlichkeit von Anwendungen erheblich verbessert werden. Weitere Informationen finden Sie unter Menü [Bänder](/windows/win32/uxguide/cmd-ribbons). Die folgende Abbildung zeigt ein Menüband.

![MFC-Menüband-Ressourcen Steuerung](../mfc/media/ribbon_no_callouts.png "MFC-Menüband-Ressourcen Steuerung")

In früheren Versionen von Visual Studio mussten Multifunktionsleisten durch Schreiben von Code erstellt werden, der die MFC-Menü Band Klassen wie die [CMFCRibbonBar-Klasse](../mfc/reference/cmfcribbonbar-class.md)verwendet. In Visual Studio 2010 und höher stellt der Menüband-Designer eine alternative Methode zum Entwickeln von Multifunktionsleisten dar. Zunächst erstellen Sie ein Menüband als Ressource und passen es an. Dann laden Sie die Menübandressource vom Code in der MFC-Anwendung. Sie können Menübandressourcen und MFC-Menübandklassen sogar zusammen verwenden. Beispielsweise können Sie eine Menü Band Ressource erstellen und der Laufzeit mithilfe von Code Programm gesteuert weitere Elemente hinzufügen.

## <a name="understanding-the-ribbon-designer"></a>Der Menüband-Designer

Mit dem Menüband-Designer wird das Menüband als Ressource erstellt und gespeichert. Wenn Sie eine Menübandressource erstellen, werden vom Menüband-Designer die folgenden drei Aktionen ausgeführt:

- Hinzufügen eines Eintrags im Projektressourcen-Definitionsskript (*.rc) Im folgenden Beispiel ist IDR_RIBBON der eindeutige Name, der die Menüband-Ressource identifiziert, RT_RIBBON_XML ist der Ressourcentyp, und Ribbon. MF cribbon-MS ist der Name der Ressourcen Datei.

```
    IDR_RIBBON RT_RIBBON_XML      "res\\ribbon.mfcribbon-ms"
```

- Hinzufügen der Definitionen von Befehls-IDs zur "resource.h"

```
#define IDR_RIBBON            307
```

- Eine Menübandressourcendatei (*.mfcribbon-ms), die den XML-Code enthält, mit dem die Schaltflächen des Menübands, die Steuerelemente und Attribute im Menüband definiert werden, wird erstellt. Änderungen, die im Menüband-Designer am Menüband vorgenommen werden, werden in der Ressourcendatei als XML gespeichert. Das folgende Codebeispiel zeigt einen Teil des Inhalts einer \*MF cribbon-MS-Datei:

```
<RIBBON_BAR>
<ELEMENT_NAME>RibbonBar</ELEMENT_NAME>
<IMAGE>
<ID>
<NAME>IDB_BUTTONS</NAME>
<VALUE>113</VALUE>
</ID>
```

Wenn Sie die Menü Band Ressource in der MFC-Anwendung verwenden möchten, laden Sie die Ressource durch Aufrufen von [CMFCRibbonBar:: loadfromresource](../mfc/reference/cmfcribbonbar-class.md#loadfromresource).

## <a name="creating-a-ribbon-by-using-the-ribbon-designer"></a>Erstellen eines Menübands mit dem Menüband-Designer

Dies sind die zwei Möglichkeiten, dem MFC-Projekt eine Menübandressource hinzuzufügen:

- Erstellen einer MFC-Anwendung und konfigurieren des MFC-Projekt-Assistenten zum Erstellen des Menübands. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer Menü Bandanwendung mithilfe von MFC](../mfc/walkthrough-creating-a-ribbon-application-by-using-mfc.md).

- Erstellen Sie in einem vorhandenen MFC-Projekt eine Menübandressource und laden Sie sie. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Aktualisieren der MFC Scribble-Anwendung (Teil 1](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)).

Wenn das Projekt bereits über ein manuell codiertes Menüband verfügt, können Sie das vorhandene Menüband mit MFC Funktionen in eine Menübandressource konvertieren. Weitere Informationen finden Sie unter [Vorgehensweise: Konvertieren eines vorhandenen MFC-Menübands in eine](../mfc/how-to-convert-an-existing-mfc-ribbon-to-a-ribbon-resource.md)Menü Band Ressource.

> [!NOTE]
>  Menübänder können nicht in Anwendungen erstellt werden, die auf Dialogfeldern basieren. Weitere Informationen finden Sie unter [Anwendungstyp, MFC-Anwendungs-Assistent](../mfc/reference/application-type-mfc-application-wizard.md).

## <a name="customizing-ribbons"></a>Anpassen von Menübändern

Um ein Menüband im Menüband-Designer zu öffnen, doppelklicken Sie in der Ressourcenansicht auf die Menübandressource. Im Designer können Sie dem Menüband, der Anwendungsschaltfläche oder der Symbolleiste für den Schnellzugriff Elemente hinzufügen, entfernen und anpassen. Sie können auch Ereignisse, z. B. Klickereignisse einer Schaltfläche und Menüereignisse, mit einer Methode in der Anwendung verknüpfen.

Die folgende Abbildung zeigt die verschiedenen Komponenten im Menüband-Designer.

![MFC-Menüband-Designer](../mfc/media/ribbon_designer.png "MFC-Menüband-Designer")

- **Stens** Enthält Steuerelemente, die auf die Designer Oberfläche gezogen werden können.

- **Oberfläche des Designers:** Enthält die visuelle Darstellung der Menüband-Ressource.

- **[Klassen-Assistent](reference/mfc-class-wizard.md):** Listet die Attribute des Elements auf, das auf der Designer Oberfläche ausgewählt ist.

- **Ressourcenansicht Fenster:** Zeigt die Ressourcen an, die Menü Band Ressourcen in Ihrem Projekt enthalten.

- **Toolbar-Editor-Symbolleiste:** Enthält Befehle, mit denen Sie eine Vorschau der Multifunktionsleiste anzeigen und das visuelle Design ändern können.

In den folgenden Themen wird die Verwendung der Funktionen im Menüband-Designer beschrieben:

- [Vorgehensweise: Anpassen der Anwendungsschaltfläche](../mfc/how-to-customize-the-application-button.md)

- [Vorgehensweise: Anpassen der Symbolleiste für den Schnellzugriff](../mfc/how-to-customize-the-quick-access-toolbar.md)

- [Vorgehensweise: Hinzufügen von Menüband-Steuerelementen und Ereignishandlern](../mfc/how-to-add-ribbon-controls-and-event-handlers.md)

- [Vorgehensweise: Laden einer Menübandressource aus einer MFC-Anwendung](../mfc/how-to-load-a-ribbon-resource-from-an-mfc-application.md)

## <a name="definitions-of-ribbon-elements"></a>Definitionen von Menübandelementen

![MFC-Menüband](../mfc/media/ribbon.png "MFC-Menüband")

- **Anwendungs Schaltfläche:** Die Schaltfläche, die in der oberen linken Ecke eines Menübands angezeigt wird. Die Anwendungsschaltfläche ersetzt das Datei-Menü und ist sichtbar, wenn das Menüband minimiert wird. Wenn auf die Schaltfläche geklickt wird, wird ein Menü mit einer Liste von Befehlen angezeigt.

- **Symbolleiste für den schnell Zugriff:** Eine kleine, anpassbare Symbolleiste, auf der häufig verwendete Befehle angezeigt werden.

- **Kategorie**: Die logische Gruppierung, die den Inhalt einer Registerkarte des Menübands darstellt.

- **Standard Schaltfläche für Kategorie:** Die Schaltfläche, die auf dem Menüband angezeigt wird, wenn das Menüband minimiert wird. Wenn auf die Schaltfläche geklickt wird, erscheint die Kategorie als Menü neu.

- **Verkleidung** Ein Bereich der Menü Band Leiste, in dem eine Gruppe verwandter Steuerelemente angezeigt wird. In jeder Menübandkategorie ist mindestens ein Menübandbereich enthalten.

- **Menü Band Elemente:** Steuerelemente in den Panels, z. b. Schaltflächen und Kombinations Felder. Die verschiedenen Steuerelemente, die auf einem Menüband gehostet werden können, [finden Sie unter ribbongadgets Sample: Menüband Gadgets](../overview/visual-cpp-samples.md)-Anwendung.

## <a name="see-also"></a>Siehe auch

[Elemente der Benutzeroberfläche](../mfc/user-interface-elements-mfc.md)<br/>
[Arbeiten mit Ressourcendateien](../windows/working-with-resource-files.md)
