---
title: '@ (Compiler-Antwortdateien festlegen) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '@'
dev_langs:
- C++
helpviewer_keywords:
- response files, C/C++ compiler
- '@ compiler option'
- cl.exe compiler, specifying response files
ms.assetid: 400fffee-909d-4f60-bf76-45833e822685
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 430e6372c1ca26e946c2ff26bfcfe9180dfb0dba
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894455"
---
# <a name="-specify-a-compiler-response-file"></a>@ (Compiler-Antwortdateien festlegen)

Gibt eine Compiler-Antwortdateien an.

## <a name="syntax"></a>Syntax

> **\@**<em>response_file</em>

## <a name="arguments"></a>Argumente

*response_file*  
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

[Compileroptionen](../../build/reference/compiler-options.md)  
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)  
