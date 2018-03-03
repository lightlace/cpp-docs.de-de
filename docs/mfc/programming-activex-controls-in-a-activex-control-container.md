---
title: 'ActiveX-Steuerelementcontainer: Programmieren von ActiveX-Steuerelementen in einem ActiveX-Steuerelementcontainer | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5a608d98b43e6daf340ab09c7adb275849f347a2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="activex-control-containers-programming-activex-controls-in-an-activex-control-container"></a>ActiveX-Steuerelementcontainer: Programmieren von ActiveX-Steuerelementen in einem ActiveX-Steuerelementcontainer
Dieser Artikel beschreibt den Prozess für den Zugriff auf den verfügbar gemachten [Methoden](../mfc/mfc-activex-controls-methods.md) und [Eigenschaften](../mfc/mfc-activex-controls-properties.md) von eingebetteten ActiveX-Steuerelementen. Im Wesentlichen müssen Sie die folgenden Schritte ausführen:  
  
1.  [Die ActiveX-Steuerelementcontainer-Projekt ein ActiveX-Steuerelement einfügen](../mfc/inserting-a-control-into-a-control-container-application.md) mit Gallery.  
  
2.  [Definieren Sie eine Membervariable](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) (oder andere Art des Zugriffs) des gleichen Typs wie die ActiveX-Wrapperklasse.  
  
3.  [Programmieren Sie das ActiveX-Steuerelement](#_core_programming_the_activex_control) mit vordefinierten Memberfunktionen der Wrapperklasse.  
  
 Bei dieser Erläuterung wird davon ausgegangen Sie, dass die Erstellung einer Dialogfeldern basierende Projektnamen (Container) mit Unterstützung für ActiveX-Steuerelement. Das daraus resultierende Projekt wird die Circ Beispiel-Steuerelement hinzugefügt.  
  
 Sobald das Circ-Steuerelement in das Projekt (Schritt 1) eingefügt wird, fügen Sie eine Instanz des Steuerelements Circ Hauptdialogfeld der Anwendung.  
  
## <a name="procedures"></a>Verfahren  
  
#### <a name="to-add-the-circ-control-to-the-dialog-template"></a>Der Dialogfeldvorlage das Circ-Steuerelement hinzu  
  
1.  Laden Sie die ActiveX-Steuerelementcontainer-Projekt. In diesem Beispiel verwendet die `Container` Projekt.  
  
2.  Klicken Sie auf der Registerkarte "Ressourcenansicht".  
  
3.  Öffnen der **Dialogfeld** Ordner.  
  
4.  Doppelklicken Sie auf die wichtigsten Dialogfeldvorlage. Verwenden Sie für dieses Beispiel **Sie IDD_CONTAINER_DIALOG**.  
  
5.  Klicken Sie auf das Symbol "Steuerelement Circ" in der Toolbox.  
  
6.  Klicken Sie auf eine Stelle nach oben im Dialogfeld auf das Steuerelement Circ einfügen.  
  
7.  Aus der **Datei** Menü wählen **alle speichern** um alle Änderungen an der Dialogfeldvorlage speichern.  
  
## <a name="modifications-to-the-project"></a>Änderungen am Projekt  
 Damit kann der Steuerelementcontainer-Anwendung auf das Steuerelement Circ, fügt Visual C++ automatisch die Wrapperklasse (`CCirc`) Implementierungsdatei (. CPP), das Container-Projekt und den klassenheader für den Wrapper (. H)-Datei in der Headerdatei für Dialogfeld-Feld:  
  
 [!code-cpp[NVC_MFC_AxCont#1](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_1.h)]  
  
##  <a name="_core_the_wrapper_class_header_28h29_file"></a>Die Header der Wrapper-Klasse (. H)-Datei  
 Zum Abrufen und Festlegen von Eigenschaften (und Aufrufen von Methoden) für das Steuerelement Circ der `CCirc` Wrapperklasse eine Deklaration alle verfügbar gemachten Methoden und Eigenschaften. In diesem Beispiel befinden sich diese Deklarationen in CIRC. H. Im folgende Beispiel ist der Teil der Klasse `CCirc` , die verfügbar gemachten Schnittstellen des ActiveX-Steuerelements definiert:  
  
 [!code-cpp[NVC_MFC_AxCont#2](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_2.h)]  
[!code-cpp[NVC_MFC_AxCont#3](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_3.h)]  
  
 Diese Funktionen können dann von anderen Prozeduren der Anwendung, die mit normaler C++-Syntax aufgerufen werden. Weitere Informationen zur Verwendung von dieser Memberfunktion legen Sie auf die Methoden und Eigenschaften des Steuerelements zugreifen, finden Sie im Abschnitt [Programmieren das ActiveX-Steuerelement](#_core_programming_the_activex_control).  
  
##  <a name="_core_member_variable_modifications_to_the_project"></a>Member Variable Änderungen am Projekt  
 Sobald das ActiveX-Steuerelement dem Projekt hinzugefügt und in einem Dialogfeld Feld Container eingebettet wurde, kann es von anderen Teilen des Projekts zugegriffen werden. Die einfachste Möglichkeit zum Zugriff auf das Steuerelement entspricht [erstellen Sie eine Membervariable](../mfc/activex-control-containers-connecting-an-activex-control-to-a-member-variable.md) der Dialogklasse, `CContainerDlg` (Schritt 2), d. h. den gleichen Typ aufweisen wie die Wrapperklasse, die dem Projekt hinzugefügt, die von Visual C++. Sie können die Membervariable klicken Sie dann auf das eingebettete Steuerelement zu einem beliebigen Zeitpunkt verwenden.  
  
 Wenn die **Hinzufügen von Membervariablen** das Dialogfeld fügt die `m_circctl` Member-Variable auf das Projekt ist, werden außerdem hinzugefügt, die folgenden Zeilen der Headerdatei (. H) von der `CContainerDlg` Klasse:  
  
 [!code-cpp[NVC_MFC_AxCont#4](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_4.h)]  
[!code-cpp[NVC_MFC_AxCont#5](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_5.h)]  
  
 Darüber hinaus einen Aufruf von **DDX_Control** wird automatisch hinzugefügt, die `CContainerDlg`der Implementierung von `DoDataExchange`:  
  
 [!code-cpp[NVC_MFC_AxCont#6](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_6.cpp)]  
  
##  <a name="_core_programming_the_activex_control"></a>Programmieren von ActiveX-Steuerelement  
 An diesem Punkt haben Sie das ActiveX-Steuerelement in der Dialogfeldvorlage eingefügt und eine Membervariable für sie erstellt. Allgemeine C++-Syntax können jetzt die Eigenschaften und Methoden des eingebetteten Steuerelements zuzugreifen.  
  
 Wie bereits erwähnt (in [der Wrapper Headerdatei (. H) Datei](#_core_the_wrapper_class_header_28h29_file)), die Headerdatei (. H) für die `CCirc` Wrapperklasse in diesem Fall CIRC. H, enthält eine Liste der Member-Funktionen, die Sie verwenden können, auf alle verfügbar gemachten Eigenschaftswert abrufen und festlegen. Memberfunktionen für verfügbar gemachten Methoden sind auch verfügbar.  
  
 So ändern Sie die Eigenschaften des Steuerelements wird häufig den `OnInitDialog` Memberfunktion der Hauptdialogfeld-Klasse. Diese Funktion wird aufgerufen, kurz bevor das Dialogfeld wird angezeigt und verwendet wird, um seinen Inhalt, einschließlich aller seiner Steuerelemente zu initialisieren.  
  
 Im folgenden Codebeispiel wird mit der `m_circctl` Membervariable beim Ändern der Beschriftung und CircleShape Eigenschaften des eingebetteten Circ Steuerelements:  
  
 [!code-cpp[NVC_MFC_AxCont#7](../mfc/codesnippet/cpp/programming-activex-controls-in-a-activex-control-container_7.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [ActiveX-Steuerelementcontainer](../mfc/activex-control-containers.md)

