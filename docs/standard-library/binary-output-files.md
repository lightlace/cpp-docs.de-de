---
title: "Binäre Ausgabedateien | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- I/O [C++], binary output files
- files [C++], binary output files
- binary data, binary output files
ms.assetid: 180954af-8cd6-444b-9a76-2f630a3389d8
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 8968a47f9d957aa0873b5db78909a6b4ad66ea75
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="binary-output-files"></a>Binäre Ausgabedateien
Streams wurden ursprünglich für Text entwickelt, deswegen ist die Standardmethode für die Ausgabe „text“. Im Textmodus erweitert das neue Zeilenumbruchzeichen (hexadezimal 10) auf einen Zeilenumbruch (nur 16-Bit) aus. Die Erweiterung kann Probleme verursachen, wie hier gezeigt wird:  
  
```  
// binary_output_files.cpp  
// compile with: /EHsc  
#include <fstream>  
using namespace std;  
int iarray[2] = { 99, 10 };  
int main( )  
{  
    ofstream os( "test.dat" );  
    os.write( (char *) iarray, sizeof( iarray ) );  
}  
```  
  
 Sie erwarten möglicherweise, dass dieses Programm die Bytesequenz { 99, 0, 10, 0 } ausgibt; stattdessen wird { 99, 0, 13, 10, 0 } ausgegeben, wodurch Probleme für ein Programm verursacht werden, das eine binäre Eingabe erwartet. Wenn sie eine echte binäre Ausgabe benötigen, in der die Zeichen nicht übersetzt geschrieben sind, können Sie die binäre Ausgabe mithilfe des openmode-Konstruktorarguments [ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream) angeben:  
  
```  
// binary_output_files2.cpp  
// compile with: /EHsc  
#include <fstream>  
using namespace std;  
int iarray[2] = { 99, 10 };  
  
int main()  
{  
   ofstream ofs ( "test.dat", ios_base::binary );  
  
   // Exactly 8 bytes written  
   ofs.write( (char*)&iarray[0], sizeof(int)*2 );   
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ausgabestreams](../standard-library/output-streams.md)


