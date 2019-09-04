---
title: Operator zum Einfügen eines Tokens (##)
ms.date: 08/29/2019
f1_keywords:
- '##'
helpviewer_keywords:
- preprocessor, operators
- '## preprocessor operator'
ms.assetid: 4f173503-990f-4bff-aef3-ec4d1f1458ef
ms.openlocfilehash: 4bf1b8c8f56ab9375503c9e8fb6a906706fc70bb
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218105"
---
# <a name="token-pasting-operator-"></a>Operator zum Einfügen eines Tokens (##)

Der Doppel Nummern Zeichen-oder tokeneinfügenden Operator ( **##** ), der manchmal als Merge- oder *kombinierungs* Operator bezeichnet wird, wird sowohl in objektähnlichen als auch in Funktions ähnlichen Makros verwendet. Sie ermöglicht es, dass getrennte Token in einem einzelnen Token verknüpft werden und daher nicht als erstes oder letztes Token in der Makro Definition zulässig sind.

Wenn ein formaler Parameter in einer Makrodefinition dem Operator „token-pasting“ voran- oder nachgestellt ist, wird der formale Parameter sofort durch das nicht erweiterte tatsächliche Argument ersetzt. Die Makroerweiterung wird nicht vor der Ersetzung für das Argument ausgeführt.

Anschließend wird jedes Vorkommen des tokeneinfügenden Operators in der *Tokenzeichenfolge* entfernt, und die vor und nachfolgend aufgeführten Token werden verkettet. Das daraus resultierende Token muss ein gültiges Token sein. Ist dies der Fall, wird das Token auf eine mögliche Ersetzung überprüft, falls es einen Makronamen darstellt. Der Bezeichner steht für den Namen, unter dem die verketteten Token vor der Ersetzung im Programm bekannt sind. Jedes Token stellt ein an anderer Stelle definiertes Token dar, entweder im Programm oder in der Compilerbefehlszeile. Leerzeichen, die dem Operator vor- oder nachgestellt sind, sind optional.

In diesem Beispiel wird die Verwendung der Zeichenfolgenoperatoren und Operatoren zum Einfügen eines Tokens beim Festlegen der Programmausgabe veranschaulicht:

```cpp
#define paster( n ) printf_s( "token" #n " = %d", token##n )
int token9 = 9;
```

Beim Aufrufen eines Makros mit einem numerischen Argument wie

```cpp
paster( 9 );
```

gibt das Makro

```cpp
printf_s( "token" "9" " = %d", token9 );
```

aus, das zu Folgendem wird:

```cpp
printf_s( "token9 = %d", token9 );
```

## <a name="example"></a>Beispiel

```cpp
// preprocessor_token_pasting.cpp
#include <stdio.h>
#define paster( n ) printf_s( "token" #n " = %d", token##n )
int token9 = 9;

int main()
{
   paster(9);
}
```

```Output
token9 = 9
```

## <a name="see-also"></a>Siehe auch

[Präprozessoroperatoren](../preprocessor/preprocessor-operators.md)
