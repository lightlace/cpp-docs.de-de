---
title: '@ (Compiler-Antwortdateien festlegen)'
ms.date: 11/04/2016
f1_keywords:
- '@'
helpviewer_keywords:
- response files, C/C++ compiler
- '@ compiler option'
- cl.exe compiler, specifying response files
ms.assetid: 400fffee-909d-4f60-bf76-45833e822685
ms.openlocfilehash: c2b5578e1ce1db590bdf5abbff0c91e858803ad7
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57808078"
---
# <a name="-specify-a-compiler-response-file"></a>@ (Compiler-Antwortdateien festlegen)

Gibt eine Compiler-Antwortdateien an.

## <a name="syntax"></a>Syntax

> **\@**<em>response_file</em>

## <a name="arguments"></a>Argumente

*response_file*<br/>
Eine Textdatei, die Compilerbefehle enthält.

## <a name="remarks"></a>Hinweise

Eine Antwortdatei kann Befehle enthalten, die Sie in der Befehlszeile angeben möchten. Dies kann nützlich sein, wenn die Befehlszeilenargumente 127 Zeichen enthalten.

Es ist nicht möglich, an die **\@** option innerhalb einer Antwortdatei. Eine Antwortdatei kann nicht, also eine andere Antwortdatei eingebettet.

Über die Befehlszeile können Sie beliebig viele Antwortdateioptionen angeben (z. B. `@respfile.1 @respfile.2`) wie gewünscht.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

- Eine Antwortdatei kann nicht in der Entwicklungsumgebung angegeben werden und muss in der Befehlszeile angegeben werden.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Diese Compileroption kann nicht programmgesteuert geändert werden.

## <a name="see-also"></a>Siehe auch

[MSVC-Compiler-Optionen](compiler-options.md)<br/>
[MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)
