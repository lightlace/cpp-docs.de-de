---
title: scanf-Breitenangaben | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apilocation:
- msvcr100.dll
- msvcr120.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- scanf
dev_langs:
- C++
helpviewer_keywords:
- scanf function, width specification
ms.assetid: 94b4e8fe-c4a2-4799-8b6c-a2cf28ffb09c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ee2fa7f80f47e2d3379bc4e68aec4496e8f4f01a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="scanf-width-specification"></a>scanf-Breitenangabe
Diese Informationen gelten für die Interpretation von Formatzeichenfolgen in der `scanf`-Funktionsreihe, einschließlich der sicheren Versionen wie `scanf_s`. Diese Funktionen nehmen in der Regel an, dass der Eingabestream in eine Folge von Token unterteilt ist. Token werden durch Leerzeichen (Leerzeichen, Tabstoppzeichen oder Zeilenumbruch) oder im Fall von numerischen Typen durch das natürliche Ende dieser getrennt, das durch das erste nicht in numerischen Text konvertierbare Zeichen angegeben ist. Mit den Breitenangaben können Sie jedoch festlegen, dass die Analyse der Eingabe vor dem natürlichen Ende eines Tokens beendet wird.  
  
 Die *Breitenangabe* besteht aus Zeichen zwischen `%` und dem Typfeldspezifizierer. Sie umfasst u.a. eine positive ganze Zahl, *Breite*-Feld genannt, und die die Größe des Felds angebenden Zeichen, die ggf. auch als Modifizierer des Feldtyps betrachtet werden können, z.B. die Angabe, ob der Ganzzahltyp **kurz** oder **lang** ist. Solche Zeichen werden als das Größenpräfix bezeichnet.  
  
## <a name="the-width-field"></a>Das Feld „Breite“  
 Das *Breite*-Feld ist eine positive ganze Dezimalzahl, die die maximale Anzahl der für dieses Feld zu lesenden Zeichen steuert. Es werden nicht mehr als die angegebenen *Breitenzeichen* konvertiert und im entsprechenden `argument` gespeichert. Weniger als die angegebenen *Breitenzeichen* werden möglicherweise gelesen, wenn ein nicht zu konvertierendes Leerstellenzeichen (Leerzeichen, Tabstoppzeichen oder Zeilenumbruch) oder ein Zeichen auftritt, bevor das Ende von *Breite* erreicht ist.  
  
 Die Breitenangabe ist unabhängig und unterscheidet sich vom Puffergrößenargument, das von den sicheren Versionen dieser Funktionen erfordert wird (z. B. `scanf_s``wscanf_s` usw.). Im folgenden Beispiel beträgt die Breitenangabe 20 und gibt somit an, dass bis zu 20 Zeichen aus dem Eingabestream gelesen werden. Die Pufferlänge beträgt 21 und schließt somit die möglichen 20 Zeichen mit dem Null-Abschlusszeichen ein:  
  
```  
char str[21];  
scanf_s("%20s", str, 21);  
```  
  
 Wenn das *Breite*-Feld nicht verwendet wird, versucht `scanf_s`, das gesamte Token in der Zeichenfolge zu lesen. Wenn die angegebene Größe nicht für das gesamte Token ausreicht, wird nichts in die Zielzeichenfolge geschrieben. Wenn das *Breite*-Feld angegeben ist, werden die ersten *Breitezeichen* im Token zusammen mit dem NULL-Abschlusszeichen in die Zielzeichenfolge geschrieben.  
  
## <a name="the-size-prefix"></a>Das Größenpräfix  
 Die optionalen Präfixe **h**, **l**, **ll**, **I64** und **L** geben die Größe des `argument` an (lang oder kurz, Einzelbytezeichen oder Breitzeichen, je nach Typzeichen, das sie ändern). Diese Formatangabezeichen werden in `scanf`- oder `wscanf`-Funktionen mit Typzeichen für die Interpretation von Argumenten verwendet, wie in der folgenden Tabelle dargestellt. Das Typpräfix **I64** ist eine Microsoft-Erweiterung und ist nicht ANSI-kompatibel. Typzeichen und ihre Bedeutungen werden in der Tabelle „Typzeichen für scanf-Funktionen“ unter [scanf-Typfeldzeichen](../c-runtime-library/scanf-type-field-characters.md) erläutert.  
  
> [!NOTE]
>  Die Präfixe **h**, **l** und **L** stellen beim Verwenden mit Daten vom Typ `char` Microsoft-Erweiterungen dar.  
  
### <a name="size-prefixes-for-scanf-and-wscanf-format-type-specifiers"></a>Größenpräfixe für die Formattypspezifizierer scanf und wscanf  
  
|Angabe von|Präfix|Mit Typspezifizierer|  
|----------------|----------------|-------------------------|  
|**double**|**l**|**e**, **E**, **f**, **g** oder **G**|  
|**long double** (identisch mit double)|**L**|**e**, **E**, **f**, **g** oder **G**|  
|**langes int**|**l**|**d**, **i**, **o**, **x** oder **X**|  
|**langes unsingniertes int**|**l**|**n**|  
|**langes long**|**ll**|**d**, **i**, **o**, **x** oder **X**|  
|`short int`|**h**|**d**, **i**, **o**, **x** oder **X**|  
|**kurzes unsigniertes int**|**h**|**u**|  
|__**int64**|**I64**|**d**, **i**, **o**, **u**, **x** oder **X**|  
|Einzelbytezeichen mit `scanf`|**h**|**c** oder **C**|  
|Einzelbytezeichen mit `wscanf`|**h**|**c** oder **C**|  
|Breitzeichen mit `scanf`|**l**|**c** oder **C**|  
|Breitzeichen mit `wscanf`|**l**|**c** oder **C**|  
|Einzelbytezeichenfolge mit `scanf`|**h**|**s** oder **S**|  
|Einzelbytezeichenfolge mit `wscanf`|**h**|**s** oder **S**|  
|Breitzeichenfolge mit `scanf`|**l**|**s** oder **S**|  
|Breitzeichenfolge mit `wscanf`|**l**|**s** oder **S**|  
  
 Die folgenden Beispiele verwenden die Präfixe **h** und **l** mit `scanf_s`- und `wscanf_s`-Funktionen:  
  
```  
scanf_s("%ls", &x, 2);     // Read a wide-character string  
wscanf_s(L"%hC", &x, 2);    // Read a single-byte character  
```  
  
 Lassen Sie beim Verwenden einer nicht sicheren Funktion in der `scanf`-Reihe den Größenparameter aus, der die Pufferlänge des vorherigen Arguments angibt.  
  
## <a name="reading-undelimited-strings"></a>Lesen von nicht durch Trennzeichen getrennten Zeichenfolgen  
 Zum Lesen von Zeichenfolgen, die nicht durch Trennzeichen getrennt sind, kann ein Zeichensatz in Klammern (**[ ]**) das **s**-Typzeichen (Zeichenfolge) ersetzen. Der Zeichensatz in Klammern wird als Steuerzeichenfolge bezeichnet. Das entsprechende Eingabefeld wird bis zum ersten Zeichen gelesen, das nicht in der Steuerzeichenfolge enthalten ist. Wenn das erste Zeichen im Satz ein Caretzeichen (**^**) ist, wird der Effekt umgekehrt: das Eingabefeld wird bis zum ersten Zeichen gelesen, das im übrigen Zeichensatz enthalten ist.  
  
 Beachten Sie, dass **%[a-z]** und **%[z-a]** auf die gleiche Weise wie **%[abcde...z]** interpretiert werden. Dies ist eine häufige `scanf`-Funktionserweiterung, beachten Sie jedoch, dass sie nicht vom ANSI-Standard erfordert wird  
  
## <a name="reading-unterminated-strings"></a>Lesen von nicht beendeten Zeichenfolgen  
 Verwenden Sie zum Speichern einer Zeichenfolge ohne ein abschließendes NULL-Zeichen („\0“) die Spezifikation `%`*n***c**, wobei *n* ein dezimaler Integerwert ist. In diesem Fall gibt das **c**-Typzeichen an, dass das Argument ein Zeiger auf ein Zeichenarray ist. Die nächsten *n*-Zeichen werden aus dem Eingabedatenstrom in die angegebene Position gelesen, und es wird kein NULL-Zeichen („\0“) angefügt. Wenn *n* nicht angegeben wird, ist der Standardwert 1.  
  
## <a name="when-scanf-stops-reading-a-field"></a>Wenn scanf das Lesen eines Felds beendet  
 Die `scanf`-Funktion überprüft Zeichen für Zeichen jedes Eingabefeld. Aus den folgenden Gründen beendet sie möglicherweise das Lesen eines bestimmten Eingabefelds, bevor ein Leerzeichen auftritt:  
  
-   Die angegebene Breite wurde erreicht.  
  
-   Das nächste Zeichen kann nicht wie angegeben konvertiert werden.  
  
-   Das nächste Zeichen weist Konflikte mit einem Zeichen in der Steuerzeichenfolge auf, mit dem es übereinstimmen soll.  
  
-   Das nächste Zeichen kann nicht in einem angegebenen Zeichensatz angezeigt werden.  
  
 Wenn die `scanf`-Funktion, unabhängig von dem Grund, das Lesen eines Eingabefelds beendet, beginnt das nächste Eingabefeld beim ersten ungelesenen Zeichen. Das einen Konflikt aufweisende Zeichen, falls vorhanden, gilt als ungelesen und stellt das erste Zeichen des nächsten Eingabefelds oder das erste Zeichen in nachfolgenden Lesevorgängen des Eingabestreams dar.  
  
## <a name="see-also"></a>Siehe auch  
 [scanf, _scanf_l, wscanf, _wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)   
 [Formatangabefelder: scanf- und wscanf-Funktionen](../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)   
 [scanf-Typenfeldzeichen](../c-runtime-library/scanf-type-field-characters.md)