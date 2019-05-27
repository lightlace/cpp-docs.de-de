---
title: /CLRUNMANAGEDCODECHECK (SuppressUnmanagedCodeSecurityAttribute entfernen)
ms.date: 05/16/2019
ms.topic: reference
f1_keywords:
- /CLRUNMANAGEDCODECHECK
helpviewer_keywords:
- -CLRUNMANAGEDCODECHECK linker option
- /CLRUNMANAGEDCODECHECK linker option
ms.assetid: 73abc426-dab0-45e2-be85-0f9a14206cc2
author: corob-msft
ms.author: corob
ms.openlocfilehash: ecc560673a8e98752289ef0e0f89d3abfc1938e4
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837241"
---
# <a name="clrunmanagedcodecheck-remove-suppressunmanagedcodesecurityattribute"></a>/CLRUNMANAGEDCODECHECK (SuppressUnmanagedCodeSecurityAttribute entfernen)

**/CLRUNMANAGEDCODECHECK** gibt an, dass der Linker <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> auf vom Linker generierte `PInvoke`-Aufrufe aus verwaltetem Code in native DLLs hinein nicht anwendet.

## <a name="syntax"></a>Syntax

> **/CLRUNMANAGEDCODECHECK**[ **:NO**]

## <a name="remarks"></a>Anmerkungen

Standardmäßig wendet der Linker das **SuppressUnmanagedCodeSecurityAttribute** auf vom Linker generierte `PInvoke`-Aufrufe an. Wenn **/CLRUNMANAGEDCODECHECK** wirksam ist, wird **SuppressUnmanagedCodeSecurityAttribute** entfernt. Um das **SuppressUnmanagedCodeSecurityAttribute** explizit auf vom Linker generierte `PInvoke`-Aufrufe anzuwenden, können Sie **/CLRUNMANAGEDCODECHECK:NO** verwenden.

Der Linker fügt das Attribut nur Objekten hinzu, die mithilfe von **/clr** oder **/clr:pure** kompiliert werden. Die Compileroption **/clr:pure** wurde allerdings in Visual Studio 2015 als veraltet erklärt und wird in Visual Studio 2017 und höher nicht mehr unterstützt.

Ein `PInvoke`-Aufruf wird vom Linker generiert, wenn der Linker kein verwaltetes Symbol finden kann, das einem Verweis von einem verwalteten Aufrufer entspricht, aber ein natives Symbol zum Bedienen des Verweises findet. Weitere Informationen zu `PInvoke` finden Sie unter [Aufrufen von nativen Funktionen aus verwaltetem Code](../../dotnet/calling-native-functions-from-managed-code.md).

Beachten Sie, dass Sie bei Verwendung von <xref:System.Security.AllowPartiallyTrustedCallersAttribute> in Ihrem Code **/CLRUNMANAGEDCODECHECK** explizit festlegen sollten, um das Attribut **SuppressUnmanagedCodeSecurity** zu entfernen. Es stellt ein potenzielles Sicherheitsrisiko dar, wenn ein Image sowohl das **SuppressUnmanagedCodeSecurity**- als auch das **AllowPartiallyTrustedCallers**-Attribut enthält.

Weitere Informationen über die Implikationen der Verwendung des **SuppressUnmanagedCodeSecurityAttribute** finden Sie unter [Richtlinien für das Schreiben von sicherem, nicht verwaltetem Code](/dotnet/framework/security/secure-coding-guidelines-for-unmanaged-code).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Erweitern Sie den Knoten **Konfigurationseigenschaften**.

1. Erweitern Sie den Knoten **Linker**.

1. Wählen Sie die Eigenschaftenseite **Erweitert** aus.

1. Ändern Sie die Eigenschaft **Überprüfung von nicht verwaltetem CLR-Code**.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRUnmanagedCodeCheck%2A>.

## <a name="see-also"></a>Siehe auch

- [MSVC-Linkerreferenz](linking.md)
- [MSVC-Linkeroptionen](linker-options.md)
