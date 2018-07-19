---
title: _environ, _wenviron | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- environ
- wenviron
- _wenviron
- _environ
dev_langs:
- C++
helpviewer_keywords:
- environ function
- _environ function
- _wenviron function
- process environment
- wenviron function
ms.assetid: 7e639962-6536-47cd-8095-0cbe44a56e03
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5f66e0aa847c0835290895aa7412410b2350d617
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2018
ms.locfileid: "34451398"
---
# <a name="environ-wenviron"></a>_environ, _wenviron
Die `_environ`-Variable ist ein Zeiger auf ein Array von Zeigern auf Multibyte-Zeichenfolgen, die die Prozessumgebung darstellen. Diese globale Variable ist für die sichereren funktionalen Versionen [getenv_s, _wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md) und [_putenv_s, _wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md) veraltet, die anstelle der globalen Variablen verwendet werden sollten. `_environ` wird in Stdlib.h deklariert.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
extern char **_environ;  
```  
  
## <a name="remarks"></a>Hinweise  
 `_environ` wird in einem Programm, das die `main`-Funktion verwendet, gemäß den Einstellungen aus der Betriebssystemumgebung beim Programmstart initialisiert. Die Umgebung besteht aus mehreren Einträgen, die folgendes Format aufweisen:  
  
 `ENVVARNAME` `=string`  
  
 `getenv_s` und `putenv_s` verwenden die `_environ`-Variable, um auf die Umgebungstabelle zuzugreifen, und diese zu bearbeiten. Beim Aufruf von `_putenv` zum Hinzufügen oder Löschen von Umgebungseinstellungen ändert sich die Größe der Umgebungstabelle. Darüber hinaus kann sich je nach Arbeitsspeicheranforderungen des Programms ihre Position im Arbeitsspeicher ändern. Der Wert von `_environ` wird dementsprechend automatisch angepasst.  
  
 Die `_wenviron`-Variable, die in STDLIB.H folgendermaßen deklariert ist,  
  
```  
extern wchar_t **_wenviron;  
```  
  
 ist eine Breitzeichenversion von `_environ`. `_wenviron` wird in einem Programm, das die `wmain`-Funktion verwendet, gemäß den Einstellungen aus der Betriebssystemumgebung beim Programmstart initialisiert.  
  
 In einem Programm, das `main` verwendet, ist `_wenviron` dementsprechend anfangs **NULL**, da die Umgebung aus Multibyte-Zeichenfolgen besteht. Beim ersten Aufruf von `_wgetenv` oder `_wputenv` wird eine entsprechende Breitzeichenumgebung erstellt, auf die von `_wenviron` gezeigt wird.  
  
 In einem Programm, das `wmain` verwendet, ist `_environ` dementsprechend anfangs **NULL**, da die Umgebung aus Breitzeichenfolgen besteht. Beim ersten Aufruf von `_getenv` oder `_putenv` wird eine entsprechende Multibytezeichen-Umgebung erstellt, auf die von `_environ` gezeigt wird.  
  
 Wenn in einem Programm zwei Kopien der Umgebung (MBCS und Unicode) gleichzeitig vorhanden sind, muss das Laufzeitsystem beide Kopien verwalten, wodurch sich die Ausführungszeit verlangsamt. Beispielsweise erfolgt bei jedem Aufruf von `_putenv` automatisch auch ein Aufruf von `_wputenv`, damit die beiden Umgebungszeichenfolgen übereinstimmen.  
  
> [!CAUTION]
>  In seltenen Fällen, wenn das Laufzeitsystem sowohl eine Unicodeversion als auch eine Multibyteversion der Umgebung verwaltet, stimmen diese zwei Versionen möglicherweise nicht exakt überein. Dies liegt daran, dass die Zuordnung von einer eindeutigen Unicodezeichenfolge zu einer Multibyte-Zeichenfolge nicht unbedingt eindeutig ist, obwohl sich jede eindeutige Multibyte-Zeichenfolge einer eindeutigen Unicodezeichenfolge zuordnen lässt. Aus diesem Grund sind möglicherweise zwei unterschiedliche Unicodezeichenfolgen der gleichen Multibyte-Zeichenfolge zugeordnet.  
  
 Der Abruf von `_environ` in einem Unicodekontext ist bei Verwendung einer [/MD](../build/reference/md-mt-ld-use-run-time-library.md)- oder `/MDd`-Verknüpfung ohne Bedeutung. Für die CRT-DLL ist der Typ des Programms (Breitzeichen oder Multibytezeichen) unbekannt. Es wird nur der Multibyte-Zeichentyp erstellt, da dies das wahrscheinlichste Szenario ist.  
  
 Im folgenden Pseudocode wird veranschaulicht, wie es dazu kommen kann.  
  
```  
int i, j;  
i = _wputenv( "env_var_x=string1" );  // results in the implicit call:  
                                      // putenv ("env_var_z=string1")  
j = _wputenv( "env_var_y=string2" );  // also results in implicit call:  
                                      // putenv("env_var_z=string2")  
```  
  
 In der für dieses Beispiel verwendeten Schreibweise stellen die Zeichenfolgen keine C-Zeichenfolgenliterale dar; vielmehr handelt es sich bei diesen um Platzhalter, die Unicodeumgebungs-Zeichenfolgenliterale im `_wputenv`-Aufruf und Multibyteumgebungs-Zeichenfolgen im `putenv`-Aufruf darstellen. Die Zeichenplatzhalter „`x`“ und „`y`“ sind in den zwei unterschiedlichen Unicode-Umgebungszeichenfolgen nicht eindeutig Zeichen in der aktuellen MBCS zugeordnet. Stattdessen sind beide dem MBCS-Zeichen „`z`“ zugeordnet, was standardmäßig das Ergebnis des Versuchs darstellt, die Zeichenfolgen zu konvertieren.  
  
 In der Multibyte-Umgebung lautet der Wert von „`env_var_z`“ folglich nach dem ersten impliziten Aufruf von `putenv` „`string1`“. Beim zweiten impliziten Aufruf von `putenv` wird dieser Wert jedoch überschrieben, wenn der Wert von „`env_var_z`“ auf „`string2`“ festgelegt ist. Die Unicodeumgebung (in `_wenviron`) und die Multibyteumgebung (in `_environ`) weicht daher nach diesen Aufrufen ab.  
  
## <a name="see-also"></a>Siehe auch  
 [Global Variables (Globale Variablen)](../c-runtime-library/global-variables.md)   
 [getenv, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)   
 [getenv_s, _wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)   
 [_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md)   
 [_putenv_s, _wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)