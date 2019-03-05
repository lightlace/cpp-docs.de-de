---
title: 'ActiveX-Steuerelementcontainer: Programmieren von ActiveX-Steuerelementen in einem ActiveX-Steuerelementcontainer'
ms.date: 09/12/2018
helpviewer_keywords:
- ActiveX control containers [MFC], accessing ActiveX controls
- Confirm Classes dialog box
- wrapper classes [MFC], ActiveX controls
- ActiveX control containers [MFC], wrapper classes
- ActiveX controls [MFC], accessing
- MFC ActiveX controls [MFC], accessing in containers
- header files [MFC], for ActiveX control wrapper class
- wrapper classes [MFC], using
- ActiveX controls [MFC], wrapper classes
ms.assetid: ef9b2480-92d6-4191-b16e-8055c4fd7b73
ms.openlocfilehash: eaeb5275ce825272e1c605e7ceeefa24db7a32ab
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57278352"
---
# <a name="activex-control-containers-programming-activex-controls-in-an-activex-control-container"></a>ActiveX-Steuerelementcontainer: Programmieren von ActiveX-Steuerelementen in einem ActiveX-Steuerelementcontainer

Dieser Artikel beschreibt den Prozess für den Zugriff auf den verfügbar gemachten [Methoden](../mfc/mfc-activex-controls-methods.md) und [Eigenschaften](../mfc/mfc-activex-controls-properties.md) eingebettete ActiveX-Steuerelemente.

>[!IMPORTANT]
> ActiveX ist eine veraltete Technologie, die nicht für Neuentwicklungen verwendet werden soll. Weitere Informationen zu moderne Technologien, die ActiveX-ablösen, finden Sie unter [ActiveX-Steuerelemente](activex-controls.md).

Im Grunde genommen, führen Sie die folgenden Schritte aus:

1. [Fügen Sie ein ActiveX-Steuerelement in das ActiveX-Container-Projekt](../mfc/inserting-a-control-into-a-control-container-application.md) Katalog verwenden.

1. [Definieren Sie eine Membervariable](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) (oder andere Art des Zugriffs) steuern, von den gleichen Typ wie die ActiveX-Wrapperklasse.

1. [Programmieren von ActiveX-Steuerelements](#_core_programming_the_activex_control) vordefinierte Memberfunktionen der Wrapperklasse.

Bei diesem Thema wird davon ausgegangen Sie, dass Sie ein dialogfeldbasiertes-Projekt (mit dem Namen "Container") erstellt haben mit ActiveX-Steuerelemente unterstützen. Die Circ Beispiel-Steuerelement aus dem wird das resultierende Projekt hinzugefügt werden.

Sobald das Circ-Steuerelement in das Projekt (Schritt 1) eingefügt wird, legen Sie eine Instanz des Steuerelements Circ in Hauptdialogfelds der Anwendung ein.

## <a name="procedures"></a>Verfahren

#### <a name="to-add-the-circ-control-to-the-dialog-template"></a>Das Steuerelement Circ Dialogfeldvorlage hinzu

1. Laden Sie das ActiveX-Steuerelement-Container-Projekt. In diesem Beispiel verwenden Sie die `Container` Projekt.

1. Klicken Sie auf der Registerkarte "Ressourcenansicht".

1. Öffnen der **Dialogfeld** Ordner.

1. Doppelklicken Sie auf die wichtigsten Dialogfeldvorlage. In diesem Beispiel verwenden **Sie IDD_CONTAINER_DIALOG**.

1. Klicken Sie auf das Symbol in der Toolbox Circ-Steuerelement.

1. Klicken Sie auf eine Stelle innerhalb des Dialogfelds, um das Steuerelement Circ einzufügen.

1. Von der **Datei** Menü wählen **Alles speichern** um alle Änderungen an der Dialogfeldvorlage speichern.

## <a name="modifications-to-the-project"></a>Änderungen am Projekt

Um die Container-Anwendung auf das Steuerelement Circ zu aktivieren, fügt Visual C++ automatisch die Wrapperklasse (`CCirc`) Implementierungsdatei (. CPP), das Container-Projekt und den klassenheader Wrapper (. H)-Datei der Dialogfeld-Box-Headerdatei:

[!code-cpp[NVC_MFC_AxCont#1](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_1.h)]

##  <a name="_core_the_wrapper_class_header_28h29_file"></a> Die Header der Wrapper-Klasse (. H)-Datei

Zum Abrufen und Festlegen von Eigenschaften (und Aufrufen von Methoden) für das Steuerelement Circ der `CCirc` Wrapper-Klasse stellt eine Deklaration alle verfügbar gemachten Methoden und Eigenschaften bereit. In diesem Beispiel befinden sich diese Deklarationen im CIRC. H. Im folgende Beispiel ist der Teil der Klasse `CCirc` , die das ActiveX-Steuerelement verfügbar gemachten Schnittstellen definiert:

[!code-cpp[NVC_MFC_AxCont#2](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_2.h)]
[!code-cpp[NVC_MFC_AxCont#3](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_3.h)]

Diese Funktionen können dann von anderen von der Anwendung-Prozeduren, die unter Verwendung normalen C++-Syntax aufgerufen werden. Weitere Informationen zur Verwendung dieser Memberfunktion, die auf Methoden und Eigenschaften des Steuerelements festlegen, finden Sie im Abschnitt [Programmieren von ActiveX-Steuerelements](#_core_programming_the_activex_control).

##  <a name="_core_member_variable_modifications_to_the_project"></a> Member Variable Änderungen am Projekt

Sobald das ActiveX-Steuerelement zum Projekt hinzugefügt und in einem Dialogfeld Feld Container eingebettet wurde, kann es von anderen Teilen des Projekts zugegriffen werden. Die einfachste Möglichkeit zum Zugriff auf das Steuerelement ist [erstellen Sie eine Membervariable](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) der Dialogklasse, `CContainerDlg` (Schritt 2), d. h. des gleichen Typs wie die Wrapperklasse, die von Visual C++ zum Projekt hinzugefügt. Sie können dann die Membervariable verwenden, auf das integrierte Steuerelement zu einem beliebigen Zeitpunkt.

Wenn die **Hinzufügen von Membervariablen** das Dialogfeld fügt die *M_circctl* Member Variablen auf das Projekt, es sowie die folgenden Zeilen der Headerdatei (. H) von der `CContainerDlg` Klasse:

[!code-cpp[NVC_MFC_AxCont#4](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_4.h)]
[!code-cpp[NVC_MFC_AxCont#5](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_5.h)]

Darüber hinaus einen Aufruf von **DDX_Control** wird automatisch hinzugefügt, die `CContainerDlg`Implementierung von `DoDataExchange`:

[!code-cpp[NVC_MFC_AxCont#6](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_6.cpp)]

##  <a name="_core_programming_the_activex_control"></a> Programmieren von ActiveX-Steuerelements

An diesem Punkt haben Sie das ActiveX-Steuerelement in Ihre Dialogfeldvorlage eingefügt und eine Membervariable erstellt. Sie können jetzt allgemeine C++-Syntax verwenden, auf die Eigenschaften und Methoden des eingebetteten Steuerelements zuzugreifen.

Wie bereits erwähnt (in [der Wrapper Headerdatei (. H) Datei](#_core_the_wrapper_class_header_28h29_file)), die Header-Datei (. H) für die `CCirc` Wrapperklasse, in diesem Fall CIRC. H, enthält eine Liste der Member-Funktionen, die Sie zum Abrufen und Festlegen der Werte aller verfügbar gemachten Eigenschaften verwenden können. Member-Funktionen für die verfügbar gemachten Methoden sind auch verfügbar.

So ändern Sie die Eigenschaften des Steuerelements wird häufig der `OnInitDialog` Memberfunktion die Hauptdialogfeldklasse. Diese Funktion wird aufgerufen, kurz bevor das Dialogfeld wird angezeigt, und verwendet wird, um seinen Inhalt, einschließlich aller seiner Steuerelemente zu initialisieren.

Im folgenden Codebeispiel wird die *M_circctl* Member-Variable, um die Beschriftung und CircleShape Eigenschaften des eingebetteten Steuerelements Circ ändern:

[!code-cpp[NVC_MFC_AxCont#7](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_7.cpp)]

## <a name="see-also"></a>Siehe auch

[ActiveX-Steuerelementcontainer](../mfc/activex-control-containers.md)
