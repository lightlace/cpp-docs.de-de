---
title: Zugreifen auf Versionsinformationen innerhalb des Programms (C++) | Microsoft-Dokumentation
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
ms.openlocfilehash: ac344242a55ba9d2f3c6ec2846feb18f70bf6483
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421517"
---
# <a name="accessing-version-information-from-within-your-program-c"></a>Zugreifen auf Versionsinformationen innerhalb des Programms (C++)

### <a name="to-access-version-information-from-within-your-program"></a>So greifen Sie aus Ihrem Programm auf Versionsinformationen zu

1. Wenn Sie die Versionsinformationen aus Ihrem Programm zugreifen möchten, verwenden Sie die [GetFileVersionInfo](/windows/desktop/api/winver/nf-winver-getfileversioninfoa) Funktion und die [VerQueryValue](/windows/desktop/api/winver/nf-winver-verqueryvaluea) Funktion.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Versionsinfo-Editor](../windows/version-information-editor.md)<br/>
[Versionsinformationen (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)