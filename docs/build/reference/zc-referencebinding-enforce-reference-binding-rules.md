---
title: /Zc:referenceBinding (Verweisbindungsregeln erzwingen)
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
ms.openlocfilehash: b7e297d6fd913ddda4d44a42298a361e314af0b5
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2020
ms.locfileid: "76518477"
---
# <a name="zcreferencebinding-enforce-reference-binding-rules"></a>/Zc:referenceBinding (Verweisbindungsregeln erzwingen)

Wenn die **/Zc: referencebinding** -Option angegeben wird, lässt der Compiler nicht zu, dass ein nicht konstanter Lvalue-Verweis an einen temporären gebunden wird.

## <a name="syntax"></a>Syntax

> **/Zc:referenceBinding**[ **-** ]

## <a name="remarks"></a>Hinweise

Wenn **/Zc: referencebinding** angegeben ist, folgt der Compiler dem Abschnitt 8.5.3 des c++ 11-Standard: er lässt keine Ausdrücke zu, die einen benutzerdefinierten Typ temporär an einen nicht konstanten Lvalue-Verweis binden. Wenn **/Zc: referencebinding-** angegeben ist, lässt der Compiler diese Ausdrücke standardmäßig als Microsoft-Erweiterung zu, es wird jedoch eine Warnung der Stufe 4 ausgegeben. Für Code Sicherheit, Portabilität und Konformität empfiehlt es sich, **/Zc: referencebinding**zu verwenden.

Die Option **/Zc: referencebinding** ist standardmäßig deaktiviert. Diese Option wird von der [/permissive-](permissive-standards-conformance.md) -Compileroption implizit festgelegt, aber Sie kann überschrieben werden, indem **/Zc: referencebinding-** verwendet wird.

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt die Microsoft-Erweiterung, mit der ein temporäres eines benutzerdefinierten Typs an einen nicht konstanten Lvalue-Verweis gebunden werden kann.

```cpp
// zcreferencebinding.cpp
struct S {
};

void f(S&) {
}

S g() {
    return S{};
}

int main() {
    S& s = g();         // warning C4239 at /W4
    const S& cs = g();  // okay, bound to const ref
    f(g());             // Extension: error C2664 only if /Zc:referenceBinding
}
```

Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Klicken Sie auf der Eigenschaftenseite auf **Konfigurationseigenschaften** > **C/C++**  > **Befehlszeile**.

1. Ändern Sie die Eigenschaft **zusätzliche Optionen** so, dass Sie **/Zc: referencebinding** einschließt, und wählen Sie dann **OK**aus.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)<br/>
[/Zc (Übereinstimmung)](zc-conformance.md)<br/>
