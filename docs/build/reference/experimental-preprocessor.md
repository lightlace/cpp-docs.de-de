---
title: '/experimental: Präprozessor (präprozessorübereinstimmungs Modus aktivieren)'
description: 'Verwenden Sie die/Experimental: präprocessor-Compileroption, um die experimentelle Compilerunterstützung für einen standardkonformen Präprozessor zu aktivieren'
ms.date: 10/31/2019
f1_keywords:
- preprocessor
- /experimental:preprocessor
helpviewer_keywords:
- preprocessor conformance
- /experimental:preprocessor
- Enable preprocessor conformance mode
ms.openlocfilehash: cb1ac63d2c12083975139455d8625544cb419adf
ms.sourcegitcommit: 2362d15b5eb18d27773c3f7522da3d0eed9e2571
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73754041"
---
# <a name="experimentalpreprocessor-enable-preprocessor-conformance-mode"></a>/experimental: Präprozessor (präprozessorübereinstimmungs Modus aktivieren)

Diese Option ermöglicht einen experimentellen, tokenbasierten Präprozessor, der den Standards von c++ 11 genauer entspricht, einschließlich C99-präprozessorfunktionen. Weitere Informationen finden Sie unter [Übersicht über den experimentellen MSVC-Präprozessor](../../preprocessor/preprocessor-experimental-overview.md).

## <a name="syntax"></a>Syntax

> **/experimental: Präprozessor**[ **-** ]

## <a name="remarks"></a>Hinweise

Verwenden Sie die **/experimental: präprocessor** -Compileroption, um den experimentellen, konformen Präprozessor zu aktivieren. Mit **/experimental: Preprocessor-** Option können Sie den herkömmlichen Präprozessor explizit angeben.

Die Option **/experimental: präprocessor** ist ab Visual Studio 2017 Version 15,8 verfügbar.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Klicken Sie auf der Eigenschaftenseite auf **Konfigurationseigenschaften** > **C/C++**  > **Befehlszeile**.

1. Ändern Sie die Eigenschaft **zusätzliche Optionen** so, dass Sie **/experimental: Preprocessor** einschließt, und wählen Sie dann **OK**aus.

## <a name="see-also"></a>Siehe auch

[/Zc (Übereinstimmung)](zc-conformance.md)
