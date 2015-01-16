#Clinical NorMA

Clinical temporal expression normaliser.

##How to use it

The normaliser can be used in two different settings.

We provide a temporal expression and an utterance time point. The normalisation
is carried out with respect to such date. The utterance time point plays a
crucial role in the normalisation of deictic temporal expressions
('today', 'a month ago', 'in two months').

    $ python clinical_norma.py 'approximately on June' 20130212
    ('approximately on june', 'DATE', '2013-06', 'Month', 'APPROX')
    
    $ python clinical_norma.py 'approximately on June' 20150212
    ('approximately on june', 'DATE', '2015-06', 'Month', 'APPROX')

You may alternatively want to provide a clinical document and a temporal expression
(format YYYYMMDD).
In this case, the document is analysed and the pivotal clinical dates are extracted
(date of admission, discharge, operation, transfer) to then be used by the normaliser
as utterance time points.

    $ python normaliser.py [file_to_analyse] 'postoperative day #4'
    ('postoperative day #4', 'DATE', '2012-01-20', 'postoperative_num1', 'NA')
    $

The output is a set of 5 elements: 1) temporal expression post-processed 2) type 3) value 4) name of the fired rule 5) modifier.

##License

(GPL v2)

Copyright (c) 2012 Michele Filannino, <http://www.cs.man.ac.uk/~filannim/>.

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 2 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.

##Contact
- Email: filannim@cs.man.ac.uk
- Web: http://www.cs.man.ac.uk/~filannim/
