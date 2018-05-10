---
title: Binär-Editor | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.binary.F1
dev_langs:
- C++
helpviewer_keywords:
- editors, Binary
- resources [Visual Studio], editing
- resource editors, Binary editor
- Binary editor
ms.assetid: 2483c48b-1252-4dbc-826b-82e6c1a0e9cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6d5deb511069830de5ea7aa542bb010f57be5af9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="binary-editor"></a>Binär-Editor
> [!WARNING]
>  Der Binär-Editor ist in Express-Editionen nicht verfügbar.  
  
 Der Binär-Editor ermöglicht eine Bearbeitung beliebige Ressourcen auf Binärebene im hexadezimalen Format oder im ASCII-Format. Außerdem können Sie mit dem [Suchbefehl](/visualstudio/ide/reference/find-command) ASCII-Zeichenfolgen oder hexadezimale Bytes suchen. Der Binär-Editor sollte nur dann verwendet werden, wenn Sie von der Visual Studio-Umgebung nicht unterstützte, benutzerdefinierte Ressourcen oder Ressourcentypen anzeigen oder geringfügige Änderungen daran vornehmen möchten.  
  
 Zum Öffnen von binären Editor wählen Sie zunächst **Datei &#124; neu &#124; Datei** über das Hauptmenü, wählen Sie die Datei, die Sie bearbeiten möchten, und dann klicken auf den Dropdownpfeil neben der **öffnen** aus, und klicken Sie **Öffnen mit &#124; Binär-Editor**.  
  
> [!CAUTION]
>  Das Bearbeiten von Ressourcen, wie Dialogfeldern, Bildern oder Menüs ist im Binär-Editor äußerst riskant. Eine falsche Bearbeitung kann zu einer Beschädigung der Ressource führen, sodass sie anschließend im systemeigenen Editor nicht mehr einsetzbar ist.  
  
> [!TIP]
>  Indem Sie im Binär-Editor auf die rechte Maustaste klicken, können Sie in vielen Situationen ein Kontextmenü aufrufen, in dem ressourcenspezifische Befehle enthalten sind. Welche Befehle verfügbar sind, hängt von dem Element ab, auf das Sie mit dem Cursor zeigen. Wenn Sie zum Beispiel mit der Maustaste klicken, während Sie auf den Binär-Editor zeigen, und im Binär-Editor Hexadezimalwerte markiert sind, enthält das Kontextmenü die Befehle **Ausschneiden**, **Kopieren**und **Einfügen** .  
  
 Mit dem Binär-Editor können Sie die folgenden Funktionen ausführen:  
  
-   [Eine Ressource für die Binärbearbeitung öffnen](../windows/opening-a-resource-for-binary-editing.md)  
  
-   [Binärdaten bearbeiten](../windows/editing-binary-data.md)  
  
-   [Binärdaten suchen](../windows/finding-binary-data.md)  
  
-   [Eine neue benutzerdefinierte Ressource oder Datenressource erstellen](../windows/creating-a-new-custom-or-data-resource.md)  
  
## <a name="managed-resources"></a>Verwaltete Ressourcen  
 Mit dem [Bild-Editor](../windows/image-editor-for-icons.md) und dem Binär-Editor ist die Bearbeitung von Ressourcendateien in verwalteten Projekten möglich. Bei den zu bearbeitenden verwalteten Ressourcen muss es sich um verknüpfte Ressourcen handeln. Das Bearbeiten eingebetteter Ressourcen wird von den Visual Studio-Ressourcen-Editoren nicht unterstützt.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
### <a name="requirements"></a>Anforderungen  
 Keiner  
  
## <a name="see-also"></a>Siehe auch  
 [Ressourcen-Editor](../windows/resource-editors.md)

