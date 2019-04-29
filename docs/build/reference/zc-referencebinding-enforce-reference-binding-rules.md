---
title: '/ Zc: referencebinding (verweisbindungsregeln erzwingen)'
ms.date: 03/06/2018
f1_keywords:
- referenceBinding
- /Zc:referenceBinding
helpviewer_keywords:
- -Zc compiler options (C++)
- referenceBinding
- Enforce reference binding rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 0c6cfaac-9c2a-41a3-aa94-64ca8ef261fc
ms.openlocfilehash: 9dfe8f5b4713d9567f6e98af6685c552fb51160e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316105"
---
# <a name="zcreferencebinding-enforce-reference-binding-rules"></a>/ Zc: referencebinding (verweisbindungsregeln erzwingen)

Wenn die **/Zc: referencebinding** angegeben wird, die der Compiler lässt sich nicht auf einen nicht Konstanten Lvalue-Verweis zum Binden an einen temporären.

## <a name="syntax"></a>Syntax

> **/Zc:referenceBinding**[**-**]

## <a name="remarks"></a>Hinweise

Wenn **/Zc: referencebinding** angegeben wird, der Compiler 8.5.3 Teil der C ++ 11-standard folgt und lässt sich nicht auf Ausdrücke, die einen benutzerdefinierten Typ temporäre auf einen nicht Konstanten Lvalue-Verweis zu binden. Standardmäßig oder wenn **/Zc:referenceBinding-** angegeben wird, der Compiler kann solche Ausdrücke als Microsoft-Erweiterung, aber es wird eine Warnung der Stufe 4 ausgegeben. Für die codesicherheit, Portierbarkeit und Konformität, empfehlen wir die Verwendung von **/Zc: referencebinding**.

Die **/Zc: referencebinding** Option ist standardmäßig deaktiviert. Die [/ PERMISSIVE--](permissive-standards-conformance.md) -Compileroption legt implizit diese Option, aber sie kann überschrieben werden, mithilfe von **/Zc:referenceBinding-**.

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt die Microsoft-Erweiterung, die eine temporäre eines benutzerdefinierten Typs in einen nicht Konstanten Lvalue-Verweis gebunden werden kann.

```cpp
// zcreferencebinding.cpp
struct S {
};

void f(S&) {
}

S g() {
    return S{};
}

void main() {
    S& s = g();         // warning C4239 at /W4
    const S& cs = g();  // okay, bound to const ref
    f(g());             // Extension: error C2664 only if /Zc:referenceBinding
}
```

Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Ändern der **zusätzliche Optionen** Eigenschaft sollen **/Zc: referencebinding** und wählen Sie dann **OK**.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)<br/>
[/Zc (Übereinstimmung)](zc-conformance.md)<br/>
