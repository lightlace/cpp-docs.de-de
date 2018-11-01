---
title: / CLRUNMANAGEDCODECHECK (Entfernen Sie SuppressUnmanagedCodeSecurityAttribute)
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- /CLRUNMANAGEDCODECHECK
helpviewer_keywords:
- -CLRUNMANAGEDCODECHECK linker option
- /CLRUNMANAGEDCODECHECK linker option
ms.assetid: 73abc426-dab0-45e2-be85-0f9a14206cc2
author: corob-msft
ms.author: corob
ms.openlocfilehash: 3cefe34eef1a30274ba2e9e362e2f61458f10e38
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50565918"
---
# <a name="clrunmanagedcodecheck-remove-suppressunmanagedcodesecurityattribute"></a>/ CLRUNMANAGEDCODECHECK (Entfernen Sie SuppressUnmanagedCodeSecurityAttribute)

**/ CLRUNMANAGEDCODECHECK** gibt an, dass der Linker nicht anwendbar ist <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> auf vom Linker generierte `PInvoke` Anrufe von verwaltetem Code aus systemeigene DLLs.

## <a name="syntax"></a>Syntax

> **/ CLRUNMANAGEDCODECHECK**[**: NO**]

## <a name="remarks"></a>Hinweise

Der Linker wendet standardmäßig die **SuppressUnmanagedCodeSecurityAttribute** auf vom Linker generierte `PInvoke` aufrufen. Wenn **/CLRUNMANAGEDCODECHECK** aktiviert ist, **SuppressUnmanagedCodeSecurityAttribute** wird entfernt. Um explizit übernehmen die **SuppressUnmanagedCodeSecurityAttribute** auf vom Linker generierte `PInvoke` aufrufen, können Sie **/CLRUNMANAGEDCODECHECK:NO**.

Der Linker fügt das Attribut nur auf Objekte, die kompiliert werden, mithilfe von **"/ CLR"** oder **/CLR: pure**. Allerdings die **/CLR: pure** Compileroption ist in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt.

Ein `PInvoke` Aufruf wird vom Linker generiert, wenn der Linker kann kein verwaltetes Symbol, um einen Verweis von einem verwalteten Aufrufer zu erfüllen, jedoch zu erfüllen, die auf ein systemeigenes Symbol gefunden. Weitere Informationen zu `PInvoke`, finden Sie unter [aufrufen nativer Funktionen aus verwaltetem Code](../../dotnet/calling-native-functions-from-managed-code.md).

Beachten Sie, dass bei Verwendung von <xref:System.Security.AllowPartiallyTrustedCallersAttribute> in Ihrem Code explizit festzulegen **/CLRUNMANAGEDCODECHECK** So entfernen Sie die **SuppressUnmanagedCodeSecurity** Attribut. Es ist ein potenzielles Sicherheitsrisiko, wenn ein Bild enthält die **SuppressUnmanagedCodeSecurity** und **AllowPartiallyTrustedCallers** Attribute.

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
