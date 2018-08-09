---
title: 'Exemplarische Vorgehensweise: Erstellen eines Standard C++-Programms (C++) | Microsoft-Dokumentation'
ms.custom: get-started-article
ms.date: 11/04/2016
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
ms.openlocfilehash: 0915f6f506b942a7ee52eec637c9ea6631339e79
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643282"
---
# <a name="walkthrough-creating-a-standard-c-program-c"></a>Exemplarische Vorgehensweise: Erstellen eines Standard C++-Programms (C++)
Mit Visual C++ können in der integrierten Entwicklungsumgebung (IDE) von Visual Studio standardmäßige C++-Programme erstellt werden. Durch Ausführen der Schritte in dieser exemplarischen Vorgehensweise können Sie ein Projekt erstellen, dem Projekt eine neue Datei hinzufügen, die Datei bearbeiten, um C++-Code hinzuzufügen und das Programm anschließend mithilfe von [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] kompilieren und ausführen.  
  
 Sie können ein eigenes C++-Programm eingeben oder eines der Beispielprogramme verwenden. Das Beispielprogramm in dieser exemplarischen Vorgehensweise ist eine Konsolenanwendung. Diese Anwendung verwendet die `set` -Container in der C++-Standardbibliothek.  
  
 Visual C++ entspricht dem 2003 C++-Standard, wobei folgende wichtigen Ausnahmen: zweistufige Namenssuche, Ausnahmespezifikationen und Export. Darüber hinaus unterstützt Visual C++ mehrere C ++ 0 X-Funktionen, z. B. Lambdas, Auto, Static_assert, Rvalue-Referenzen und Extern-Vorlagen.  
  
> [!NOTE]
>  Wenn Kompatibilität mit dem Standard erforderlich ist, verwenden Sie die `/Za`-Compileroption, um Microsoft-Erweiterungen für den Standard zu deaktivieren. Weitere Informationen finden Sie unter [/Za, / Ze (Spracherweiterungen deaktivieren)](../build/reference/za-ze-disable-language-extensions.md).  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Zur Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Grundkenntnisse in C++.  
  
### <a name="to-create-a-project-and-add-a-source-file"></a>So erstellen Sie ein neues Projekt und fügen eine Quelldatei hinzu  
  
1.  Erstellen Sie ein Projekt, zeigen Sie dazu **neu** auf die **Datei** Menü, und klicken Sie dann auf **Projekt**.  
  
2.  In der **Visual C++** Bereich "Projekttypen", klicken Sie auf **Windows Desktop**, und klicken Sie dann auf **Windows-Konsolenanwendung**.  
  
3.  Geben Sie einen Namen für das Projekt ein.  
  
     Standardmäßig erhält die Lösung, in der das Projekt enthalten ist, den gleichen Namen wie das Projekt. Sie können jedoch auch einen anderen Namen eingeben. Sie können auch einen anderen Speicherort für das Projekt eingeben.  
  
     Klicken Sie auf **OK**, um das Projekt zu erstellen.  
  
4.  Wenn **Projektmappen-Explorer** nicht angezeigt wird, auf die **Ansicht** Menü klicken Sie auf **Projektmappen-Explorer**.  
  
5.  Fügen Sie dem Projekt folgendermaßen eine neue Quelldatei hinzu:  
  
    1.  In **Projektmappen-Explorer**, mit der rechten Maustaste die **Quelldateien** Ordner, zeigen Sie auf **hinzufügen**, und klicken Sie dann auf **neues Element**.  
  
    2.  In der **Code** Knoten, klicken Sie auf **C++-Datei (.cpp)**, geben Sie einen Namen für die Datei, und klicken Sie dann auf **hinzufügen**.  
  
     Die CPP-Datei wird im Ordner "Quelldateien" in **Projektmappen-Explorer**, und die Datei in Visual Studio-Editor geöffnet ist.  
  
6.  Geben Sie in der Datei im Editor ein gültiges C++-Programm, das die C++-Standardbibliothek verwendet, oder kopieren Sie eines der Beispielprogramme, und fügen Sie ihn in der Datei.  
  
7.  Speichern Sie die Datei.  
  
8. Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.  
  
     Die **Ausgabe** werden Informationen zum Kompilierungsprozess angezeigt, z. B. den Speicherort des Buildprotokolls und eine Nachricht, die den Buildstatus.  
  
9. Klicken Sie im Menü **Debuggen** auf **Starten ohne Debuggen**.  
  
     Wenn Sie das Beispielprogramm verwendet haben, wird ein Befehlsfenster angezeigt. Dieses gibt an, ob bestimmte ganze Zahlen im Set enthalten sind.  
  
## <a name="next-steps"></a>Nächste Schritte  
 **Zurück:** [Konsolenanwendungen in Visual C++](../windows/console-applications-in-visual-cpp.md). **Nächster Schritt:**[Exemplarische Vorgehensweise: Kompilieren eines nativen C++-Programms in der Befehlszeile](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md).  
  
## <a name="see-also"></a>Siehe auch  
 [C++ Language Reference (C++-Programmiersprachenreferenz)](../cpp/cpp-language-reference.md)   
 [C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)