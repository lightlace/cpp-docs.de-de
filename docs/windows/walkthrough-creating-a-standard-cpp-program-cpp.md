---
title: 'Exemplarische Vorgehensweise: Erstellen eines Standard C++-Programms (C++)'
ms.custom: get-started-article
ms.date: 04/25/2019
helpviewer_keywords:
- command-line applications [C++], standard
- standard applications [C++]
ms.assetid: 48217e35-d892-46b7-93e3-f6f0b7e2da35
ms.openlocfilehash: ed9c19dad029f8fc9495d38ab6e5c0ba8ad6d529
ms.sourcegitcommit: 18d3b1e9cdb4fc3a76f7a650c31994bdbd2bde64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2019
ms.locfileid: "64877418"
---
# <a name="walkthrough-creating-a-standard-c-program-c"></a>Exemplarische Vorgehensweise: Erstellen eines Standard C++-Programms (C++)

Sie können Visual Studio verwenden, um Standard zu erstellen C++ Programme. Mithilfe der Schritte in dieser exemplarischen Vorgehensweise können erstellen Sie ein Projekt, fügen dem Projekt eine neue Datei, die Datei, um C++-Code hinzuzufügen, klicken Sie dann zu kompilieren und führen Sie das Programm mit Visual Studio ändern.

Sie können ein eigenes C++-Programm eingeben oder eines der Beispielprogramme verwenden. Das Beispielprogramm in dieser exemplarischen Vorgehensweise ist eine Konsolenanwendung. Diese Anwendung verwendet die `set` -Container in der C++-Standardbibliothek.

> [!NOTE]
> Wenn Kompatibilität mit einer bestimmten Version der C++ Sprachstandard (z. B. C ++ 14 oder C ++ 17) erforderlich ist, verwenden die `/std:C++14` oder `/std:c++17` -Compileroption. (Visual Studio 2017 und höher.)

## <a name="prerequisites"></a>Vorraussetzungen

Zur Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Grundkenntnisse in C++.

### <a name="to-create-a-project-and-add-a-source-file"></a>So erstellen Sie ein neues Projekt und fügen eine Quelldatei hinzu

Die folgenden Schritte hängen davon ab, welche Version von Visual Studio Sie verwenden. Stellen Sie sicher, dass die Auswahl für die Version in der oberen linken Rand dieser Seite richtig festgelegt ist.

::: moniker range="vs-2019"

### <a name="to-create-a-c-project-in-visual-studio-2019"></a>Zum Erstellen einer C++ -Projekt in Visual Studio-2019

1. Wählen Sie im Hauptmenü **Datei** > **neu** > **Projekt** zum Öffnen der **Erstellen eines neuen Projekts** Dialogfeld Box.

1. Legen Sie am oberen Rand des Dialogfelds, **Sprache** zu **C++** legen **Plattform** zu **Windows**, und legen Sie **Projekttyp** zu **Konsole**. 

1. Wählen Sie die gefilterte Liste der Projekttypen, **Konsolen-App** wählen Sie dann **Weiter**. Klicken Sie in der nächsten Seite Geben Sie einen Namen für das Projekt, und geben Sie den Speicherort des Projekts ein, bei Bedarf.

1. Wählen Sie die **erstellen** klicken, um das Projekt zu erstellen.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-c-project-in-visual-studio-2017"></a>Zum Erstellen einer C++ -Projekt in Visual Studio 2017

1. Erstellen Sie ein Projekt, zeigen Sie dazu **neu** auf die **Datei** Menü, und klicken Sie dann auf **Projekt**.

1. In der **Visual C++** Bereich "Projekttypen", klicken Sie auf **Windows Desktop**, und klicken Sie dann auf **Windows-Konsolenanwendung**.

1. Geben Sie einen Namen für das Projekt ein. Standardmäßig erhält die Lösung, in der das Projekt enthalten ist, den gleichen Namen wie das Projekt. Sie können jedoch auch einen anderen Namen eingeben. Sie können auch einen anderen Speicherort für das Projekt eingeben.

1. Klicken Sie auf **OK**, um das Projekt zu erstellen.

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-c-project-in-visual-studio-2015"></a>Zum Erstellen einer C++ Projekt in Visual Studio 2015

1. Erstellen Sie ein Projekt, zeigen Sie dazu **neu** auf die **Datei** Menü, und klicken Sie dann auf **Projekt**.

1. In der **Visual C++** Bereich "Projekttypen", klicken Sie auf **Windows Desktop**, und klicken Sie dann auf **Windows-Konsolenanwendung**.

1. In der **neues Projekt** Dialogfeld erweitern Sie **installiert** > **Vorlagen** > **Visual C++** , und Wählen Sie dann **Win32**. Wählen Sie im mittleren Bereich **Win32-Konsolenanwendung**aus.

1. Geben Sie einen Namen für das Projekt ein. Standardmäßig erhält die Lösung, in der das Projekt enthalten ist, den gleichen Namen wie das Projekt. Sie können jedoch auch einen anderen Namen eingeben. Sie können auch einen anderen Speicherort für das Projekt eingeben.

1. Klicken Sie auf **OK**, um das Projekt zu erstellen.

1. Abschließen der **Win32-Anwendungsassistenten**. 

1. Klicken Sie auf **Weiter**, dann stellen Sie sicher, dass **Konsolenanwendung** ausgewählt ist, und deaktivieren Sie die **vorkompilierte Header** Feld. 

1. Klicken Sie auf **Fertig stellen**.

::: moniker-end

## <a name="add-a-new-source-file"></a>Fügen Sie eine neue Quelldatei hinzu

1. Wenn **Projektmappen-Explorer** wird nicht angezeigt, auf die **Ansicht** Menü klicken Sie auf **Projektmappen-Explorer**.

1. Fügen Sie dem Projekt folgendermaßen eine neue Quelldatei hinzu:

   1. In **Projektmappen-Explorer**, mit der rechten Maustaste die **Quelldateien** Ordner, zeigen Sie auf **hinzufügen**, und klicken Sie dann auf **neues Element**.

   1. In der **Code** Knoten, klicken Sie auf **C++-Datei (.cpp)**, geben Sie einen Namen für die Datei, und klicken Sie dann auf **hinzufügen**.

   Die CPP-Datei wird angezeigt, der **Quelldateien** Ordner **Projektmappen-Explorer**, und die Datei in Visual Studio-Editor geöffnet ist.

1. Geben Sie in der Datei im Editor ein gültiges C++-Programm, das die C++-Standardbibliothek verwendet, oder kopieren Sie eines der Beispielprogramme, und fügen Sie ihn in der Datei.

1. Speichern Sie die Datei.

1. Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.

   Die **Ausgabe** werden Informationen zum Kompilierungsprozess angezeigt, z. B. den Speicherort des Buildprotokolls und eine Nachricht, die den Buildstatus.

1. Klicken Sie im Menü **Debuggen** auf **Starten ohne Debuggen**.

   Wenn Sie das Beispielprogramm verwendet haben, wird ein Befehlsfenster angezeigt. Dieses gibt an, ob bestimmte ganze Zahlen im Set enthalten sind.

## <a name="next-steps"></a>Nächste Schritte

**Zurück:** [Konsolenanwendungen für Visual C++](../windows/console-applications-in-visual-cpp.md)<br/>
**Weiter:** [Exemplarische Vorgehensweise: Kompilieren eines nativen C++-Programms in der Befehlszeile](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)<br/>

## <a name="see-also"></a>Siehe auch

[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)<br/>
