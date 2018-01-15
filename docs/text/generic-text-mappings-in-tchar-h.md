---
title: Zuordnen von generischem Text in Tchar.h | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: tchar.h
dev_langs: C++
helpviewer_keywords:
- mapping generic-text
- generic-text mappings [C++]
- character sets [C++], generic-text mappings
- Unicode [C++], generic-text mappings
- MBCS [C++], generic-text mappings
- TCHAR.H data types, mapping
- mappings [C++], TCHAR.H
ms.assetid: 01e1bb74-5a01-4093-8720-68b6c1fdda80
caps.latest.revision: "12"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 405e95e9eb8fb760e2688e164178cf9270f31877
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="generic-text-mappings-in-tcharh"></a>Zuordnungen für generischen Text in Tchar.h
Um die Codeübertragung für internationale Anwendungen zu vereinfachen, stellt die [!INCLUDE[TLA#tla_ms](../text/includes/tlasharptla_ms_md.md)]-Laufzeitbibliothek [!INCLUDE[TLA#tla_ms](../text/includes/tlasharptla_ms_md.md)]-spezifische Zuordnungen für generischen Text für viele Datentypen, Routinen und andere Objekte zur Verfügung. Mit diesen Zuordnungen, die in Tchar.h definiert sind, können Sie generischen Code schreiben, der für Einzelbyte-, Mehrbyte- oder [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)]-Zeichensätze kompiliert werden kann, abhängig von einer eindeutigen Konstante, die Sie mithilfe einer `#define`-Anweisung definieren. Zuordnungen für generischen Text sind [!INCLUDE[TLA#tla_ms](../text/includes/tlasharptla_ms_md.md)]-Erweiterungen, die nicht [!INCLUDE[vcpransi](../atl-mfc-shared/reference/includes/vcpransi_md.md)]-kompatibel sind.  
  
 Mit Tchar.h können Sie Einzelbyte-, MBCS- (Mehrbyte-Zeichensätze) und [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)]-Anwendungen aus denselben Quellen erstellen. Mit Tchar.h werden Makros (mit dem Präfix `_tcs`) definiert, die der Funktion `str`, `_mbs` oder `wcs` zugeordnet werden, vorausgesetzt, die Präprozessordefinitionen sind richtig. Definieren Sie zur Erstellung von MBCS das `_MBCS`-Symbol. Definieren Sie zur Erstellung von [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] das `_UNICODE`-Symbol. Um eine Einzelbyte-Anwendung zu erstellen, geben Sie nichts an (Standardeinstellung). Standardmäßig wird `_MBCS` für MFC-Anwendungen definiert.  
  
 Der `_TCHAR`-Datentyp wird in Tchar.h bedingt definiert. Wenn das `_UNICODE`-Symbol für den jeweiligen Build definiert ist, wird `_TCHAR` als `wchar_t` definiert. Andernfalls (für Einzelbyte- und MBCS-Builds) wird er als `char` definiert. (`wchar_t`, der Unicode-Basisdatentyp für Breitzeichen, ist das 16-Bit-Gegenstück zum 8-Bit-Datentyp `char` mit Vorzeichen.) Verwenden Sie für internationale Anwendungen die `_tcs`-Funktionsreihe, bei der anstelle von Bytes `_TCHAR`-Einheiten verwendet werden. Beispielsweise `_tcsncpy` Kopien `n` `_TCHARs`, nicht `n` Bytes.  
  
 Da für einige Funktionen zur Zeichenfolgenbehandlung bei Einzelbyte-Zeichensätzen (SBCS) `char*`-Parameter (mit Vorzeichen) erforderlich sind, wird bei der Definition von `_MBCS` eine Compiler-Warnung ausgegeben, die auf einen Typenkonflikt hinweist. Es gibt drei Möglichkeiten, diese Warnung zu vermeiden:  
  
1.  Verwenden Sie die typsicheren Inlinefunktionsthunks in Tchar.h. Dies ist das Standardverhalten.  
  
2.  Verwenden Sie die direkten Makros in Tchar.h, indem Sie in der Befehlszeile `_MB_MAP_DIRECT` definieren. In diesem Fall müssen Sie die Typübereinstimmung manuell sicherstellen. Dies ist die schnellste Methode; sie ist jedoch nicht typsicher.  
  
3.  Verwenden Sie die typsicheren statisch verknüpften Bibliotheksfunktionsthunks in Tchar.h. Definieren Sie hierzu in der Befehlszeile die Konstante `_NO_INLINING`. Dies ist die langsamste Methode; sie bietet jedoch auch die größte Typsicherheit.  
  
### <a name="preprocessor-directives-for-generic-text-mappings"></a>Präprozessordirektiven zum Zuordnen von generischem Text  
  
|#define|Kompilierte Version|Beispiel|  
|---------------|----------------------|-------------|  
|`_UNICODE`|[!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] (Breitzeichen)|`_tcsrev` wird `_wcsrev` zugeordnet.|  
|`_MBCS`|Mehrbytezeichen|`_tcsrev` wird `_mbsrev` zugeordnet.|  
|Keine (bei der Standardeinstellung ist weder `_UNICODE` noch `_MBCS` definiert)|SBCS ([!INCLUDE[TLA#tla_ascii](../text/includes/tlasharptla_ascii_md.md)])|`_tcsrev` wird `strrev` zugeordnet.|  
  
 Die in Tchar.h definierte generische Textfunktion `_tcsrev` wird z. B. der `_mbsrev`-Funktion zugeordnet, wenn Sie `_MBCS` in einem Programm definiert haben, oder sie wird `_wcsrev` zugeordnet, wenn Sie `_UNICODE` definiert haben. Andernfalls wird `_tcsrev` `strrev` zugeordnet. Zur Vereinfachung der Programmierung werden in Tchar.h weitere Datentypzuordnungen zur Verfügung gestellt; `_TCHAR` ist jedoch die hilfreichste Zuordnung.  
  
### <a name="generic-text-data-type-mappings"></a>Generische Textzuordnungen von Datentypen  
  
|Generischer Text<br /><br /> Datentypname|_UNICODE &<br /><br /> _MBCS nicht definiert|_MBCS<br /><br /> Definiert|_UNICODE<br /><br /> Definiert|  
|--------------------------------------|----------------------------------------|------------------------|---------------------------|  
|`_TCHAR`|`char`|`char`|`wchar_t`|  
|`_TINT`|`int`|`unsigned int`|`wint_t`|  
|`_TSCHAR`|`signed char`|`signed char`|`wchar_t`|  
|`_TUCHAR`|`unsigned char`|`unsigned char`|`wchar_t`|  
|`_TXCHAR`|`char`|`unsigned char`|`wchar_t`|  
|`_T` oder `_TEXT`|Ohne Auswirkung (wird vom Präprozessor entfernt)|Ohne Auswirkung (wird vom Präprozessor entfernt)|`L`(wandelt das folgende Zeichen oder eine Zeichenfolge, die die [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] Entsprechung)|  
  
 Eine Liste der Zuordnungen für generischen Text von Routinen, Variablen und andere Objekte, finden Sie unter [Zuordnen von generischem Text](../c-runtime-library/generic-text-mappings.md) in die Run-Time Library Reference.  
  
> [!NOTE]
>  Verwenden Sie die `str`-Funktionsreihe nicht mit Unicode-Zeichenfolgen, da diese wahrscheinlich eingebettete NULL-Bytes enthalten. Ebenso sollten Sie die `wcs`-Funktionsreihe nicht mit Zeichenfolgen vom Typ MBCS (oder SBCS) verwenden.  
  
 Aus den folgenden Codeausschnitten geht hervor, wie `_TCHAR` und `_tcsrev` für die Zuordnung zu den MBCS-, [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)]- und SBCS-Modellen verwendet werden.  
  
```  
_TCHAR *RetVal, *szString;  
RetVal = _tcsrev(szString);  
```  
  
 Wenn `_MBCS` definiert wurde, ordnet der Präprozessor diesem Code folgenden Ausschnitt zu:  
  
```  
char *RetVal, *szString;  
RetVal = _mbsrev(szString);  
```  
  
 Wenn `_UNICODE` definiert wurde, ordnet der Präprozessor diesem Code folgenden Ausschnitt zu:  
  
```  
wchar_t *RetVal, *szString;  
RetVal = _wcsrev(szString);  
```  
  
 Wenn weder `_MBCS` noch `_UNICODE` definiert wurde, ordnet der Präprozessor dem Einzelbyte-[!INCLUDE[TLA#tla_ascii](../text/includes/tlasharptla_ascii_md.md)]-Code den Ausschnitt wie folgt zu:  
  
```  
char *RetVal, *szString;  
RetVal = strrev(szString);  
```  
  
 Folglich können Sie eine einzige Quellcodedatei so schreiben, verwalten und kompilieren, dass sie mit Routinen ausgeführt wird, die jeweils speziell auf einen der drei Zeichensätze ausgerichtet sind.  
  
## <a name="see-also"></a>Siehe auch  
 [Text und Zeichenfolgen](../text/text-and-strings-in-visual-cpp.md)   
 [Verwenden von TCHAR.H-Datentypen in _MBCS-Code](../text/using-tchar-h-data-types-with-mbcs-code.md)