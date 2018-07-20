---
title: Bearbeiten einer Zeichenfolge in einer Versionsinformationsressource | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.version
dev_langs:
- C++
helpviewer_keywords:
- version information resources
- resources [Visual Studio], editing version information
ms.assetid: d3a7d4e4-7d31-47c2-902c-f50b8404ba4f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 80795f912ab41809b19e77bd33f56243541d4de1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33882883"
---
# <a name="editing-a-string-in-a-version-information-resource"></a>Bearbeiten einer Zeichenfolge in einer Versionsinforessource
### <a name="to-edit-a-string-in-a-version-information-resource"></a>So bearbeiten Sie eine Zeichenfolge in einer Versionsinformationsressource  
  
1.  Klicken Sie ein Mal auf das Element, um es auszuwählen, und dann noch ein Mal, um mit der Bearbeitung zu beginnen. Nehmen Sie die Änderungen direkt in der Versionsinformationstabelle oder im [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window)vor. Die vorgenommenen Änderungen werden an beiden Orten berücksichtigt.  
  
     **Hinweis** Beim Bearbeiten des **FILEFLAGS** -Schlüssels im Versionsinformations-Editor werden Sie bemerken, dass Sie die Eigenschaften **Debug**, **Private Build**oder **Special Build** (im Eigenschaftenfenster) für RC-Dateien nicht festlegen können:  
  
    -   Der Versionsinformations-Editor legt die Eigenschaft **Debug** mit einer #ifdef-Direktive im Ressourcenskript fest, basierend auf dem **_DEBUG** -Build-Flag.  
  
    -   Wenn für den **Private Build** -Schlüssel ein **Wert** in der Versionsinformationstabelle festgelegt ist, ist die entsprechende **Private Build** -Eigenschaft (im Eigenschaftenfenster) für den **FILEFLAGS** -Schlüssel auf **True**festgelegt. Wenn der **Wert** leer ist, ist die Eigenschaft **False**. Analog dazu ist der **Special Build** -Schlüssel (in der Versionsinformationstabelle) an die **Special Build** -Eigenschaft für den **FILEFLAGS** -Schlüssel gebunden.  
  
 Sie können die Informationssequenz des Zeichenfolgenblocks sortieren, indem Sie entweder auf den Spaltenkopf „Schlüssel“ oder den Spaltenkopf „Wert“ klicken. Mithilfe dieser Überschriften können die Informationen automatisch in der ausgewählten Reihenfolge neu angeordnet werden.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
 **Anforderungen**  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Versionsinfo-Editor](../windows/version-information-editor.md)   
 [Versionsinformationen (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)

