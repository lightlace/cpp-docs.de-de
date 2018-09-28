---
title: / CLRUNMANAGEDCODECHECK (Hinzufügen von SuppressUnmanagedCodeSecurity) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /CLRUNMANAGEDCODECHECK
dev_langs:
- C++
helpviewer_keywords:
- -CLRUNMANAGEDCODECHECK linker option
- /CLRUNMANAGEDCODECHECK linker option
ms.assetid: 73abc426-dab0-45e2-be85-0f9a14206cc2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 679adc527cc70056e1292eb7e639499bd814bca6
ms.sourcegitcommit: 7838764e09819822a105accf5d773b2e37ffa0ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2018
ms.locfileid: "47429760"
---
# <a name="clrunmanagedcodecheck-add-suppressunmanagedcodesecurityattribute"></a>/ CLRUNMANAGEDCODECHECK (Hinzufügen von SuppressUnmanagedCodeSecurity)

**/ CLRUNMANAGEDCODECHECK** gibt an, ob der Linker anwendet <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> auf vom Linker generierte `PInvoke` Anrufe von verwaltetem Code aus systemeigene DLLs.

## <a name="syntax"></a>Syntax

> **/ CLRUNMANAGEDCODECHECK**[**: NO**]

## <a name="remarks"></a>Hinweise

Der Linker wendet standardmäßig die **SuppressUnmanagedCodeSecurityAttribute** auf vom Linker generierte `PInvoke` aufrufen. Wenn **/CLRUNMANAGEDCODECHECK** aktiviert ist, **SuppressUnmanagedCodeSecurityAttribute** wird nicht angewendet.

Der Linker das Attribut nur auf Objekte, die mit kompiliert werden, hinzugefügt **"/ CLR"** oder **/CLR: pure**. Allerdings die **/CLR: pure** Compileroption ist in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt.

Ein `PInvoke` Aufruf wird vom Linker generiert, wenn der Linker kann kein verwaltetes Symbol, um einen Verweis von einem verwalteten Aufrufer zu erfüllen, jedoch zu erfüllen, die auf ein systemeigenes Symbol gefunden. Weitere Informationen zu `PInvoke`, finden Sie unter [aufrufen nativer Funktionen aus verwaltetem Code](../../dotnet/calling-native-functions-from-managed-code.md).

Beachten Sie, dass bei Verwendung von <xref:System.Security.AllowPartiallyTrustedCallersAttribute> in Ihrem Code explizit festzulegen **/CLRUNMANAGEDCODECHECK**. Es ist Sicherheitsrisiko, wenn ein Bild SuppressUnmanagedCodeSecurity sowohl AllowPartiallyTrustedCallers-Attribut enthält.

Finden Sie unter [Secure Coding Guidelines für nicht verwalteten Code](/dotnet/framework/security/secure-coding-guidelines-for-unmanaged-code) für Weitere Informationen zu den Auswirkungen der Verwendung von **SuppressUnmanagedCodeSecurityAttribute**.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Erweitern Sie den Knoten **Konfigurationseigenschaften**.

1. Erweitern Sie die **Linker** Knoten.

1. Wählen Sie die **erweitert** Eigenschaftenseite.

1. Ändern der **CLR nicht verwalteten Code überprüfen** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRUnmanagedCodeCheck%2A>.

## <a name="see-also"></a>Siehe auch

- [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)
- [Linkeroptionen](../../build/reference/linker-options.md)
