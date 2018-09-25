---
title: 'Exemplarische Vorgehensweise: Erstellen eines Standard C++-Programms (C++) | Microsoft-Dokumentation'
ms.custom: get-started-article
ms.date: 09/18/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vcfirstapp
- vccreatefirst
dev_langs:
- C++
helpviewer_keywords:
- command-line applications [C++], standard
- standard applications [C++]
ms.assetid: 48217e35-d892-46b7-93e3-f6f0b7e2da35
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d5481b9391d47887d85ca43746f1a6aff5f6eb92
ms.sourcegitcommit: 92c568e9466ffd7346a4120c478c9bdea61c8756
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2018
ms.locfileid: "47029618"
---
# <a name="walkthrough-creating-a-standard-c-program-c"></a>Exemplarische Vorgehensweise: Erstellen eines Standard C++-Programms (C++)

Mit Visual C++ können in der integrierten Entwicklungsumgebung (IDE) von Visual Studio standardmäßige C++-Programme erstellt werden. Mithilfe der Schritte in dieser exemplarischen Vorgehensweise können erstellen Sie ein Projekt, fügen dem Projekt eine neue Datei, die Datei, um C++-Code hinzuzufügen, klicken Sie dann zu kompilieren und führen Sie das Programm mit Visual Studio ändern.

Sie können ein eigenes C++-Programm eingeben oder eines der Beispielprogramme verwenden. Das Beispielprogramm in dieser exemplarischen Vorgehensweise ist eine Konsolenanwendung. Diese Anwendung verwendet die `set` -Container in der C++-Standardbibliothek.

Visual C++ entspricht dem 2003 C++-Standard, wobei folgende wichtigen Ausnahmen: zweistufige Namenssuche, Ausnahmespezifikationen und Export. Darüber hinaus unterstützt Visual C++ mehrere C ++ 0 X-Funktionen, z. B. Lambdas, Auto, Static_assert, Rvalue-Referenzen und Extern-Vorlagen.

> [!NOTE]
> Wenn Kompatibilität mit dem Standard erforderlich ist, verwenden Sie die `/Za`-Compileroption, um Microsoft-Erweiterungen für den Standard zu deaktivieren. Weitere Informationen finden Sie unter [/Za, / Ze (Spracherweiterungen deaktivieren)](../build/reference/za-ze-disable-language-extensions.md).

## <a name="prerequisites"></a>Erforderliche Komponenten

Zur Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Grundkenntnisse in C++.

### <a name="to-create-a-project-and-add-a-source-file"></a>So erstellen Sie ein neues Projekt und fügen eine Quelldatei hinzu

1. Erstellen Sie ein Projekt, zeigen Sie dazu **neu** auf die **Datei** Menü, und klicken Sie dann auf **Projekt**.

1. In der **Visual C++** Bereich "Projekttypen", klicken Sie auf **Windows Desktop**, und klicken Sie dann auf **Windows-Konsolenanwendung**. 

   > [!NOTE]
   > Für Versionen von Visual Studio, die älter als 2017 in der **neues Projekt** Dialogfeld erweitern Sie **installiert** > **Vorlagen**  >  **Visual C++**, und wählen Sie dann **Win32**. Wählen Sie im mittleren Bereich **Win32-Konsolenanwendung**aus. 

   Geben Sie einen Namen für das Projekt ein.

   Standardmäßig erhält die Lösung, in der das Projekt enthalten ist, den gleichen Namen wie das Projekt. Sie können jedoch auch einen anderen Namen eingeben. Sie können auch einen anderen Speicherort für das Projekt eingeben.

   Klicken Sie auf **OK**, um das Projekt zu erstellen.

   > [!NOTE]
   > Führen Sie für die Versionen von Visual Studio, die älter als 2017, die **Win32-Anwendungsassistenten**. Klicken Sie auf **Weiter**, dann stellen Sie sicher, dass **Konsolenanwendung** ausgewählt ist, und deaktivieren Sie die **vorkompilierte Header** Feld. Klicken Sie auf **Fertig stellen**.

1. Wenn **Projektmappen-Explorer** nicht angezeigt wird, auf die **Ansicht** Menü klicken Sie auf **Projektmappen-Explorer**.

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

**Zurück:** [Konsolenanwendungen in Visual C++](../windows/console-applications-in-visual-cpp.md)<br/>
**Nächster Schritt:** [Exemplarische Vorgehensweise: Kompilieren eines nativen C++-Programms in der Befehlszeile](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)<br/>

## <a name="see-also"></a>Siehe auch

[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)<br/>
