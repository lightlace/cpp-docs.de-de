---
title: Zugreifen auf Versionsinformationen innerhalb des Programms | Microsoft Docs
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
- VerQueryValue
- version information, accessing from within programs
- GetFileVersionInfo
- version information
ms.assetid: 18622333-d9e8-4309-9465-677cd10c79b1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e8913e0dc33da1de2f240305ff19f5250e38b180
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="accessing-version-information-from-within-your-program"></a>Zugreifen auf Versionsinformationen innerhalb des Programms
### <a name="to-access-version-information-from-within-your-program"></a>So greifen Sie aus Ihrem Programm auf Versionsinformationen zu  
  
1.  Wenn Sie aus ihrem Programm auf die Versionsinformationen zugreifen möchten, verwenden Sie die Funktion [GetFileVersionInfo](http://msdn.microsoft.com/library/windows/desktop/ms647003.aspx) und die Funktion [VerQueryValue](http://msdn.microsoft.com/library/windows/desktop/ms647464.aspx) .  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
 **Anforderungen**  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Versionsinfo-Editor](../windows/version-information-editor.md)   
 [Versionsinformationen (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)

