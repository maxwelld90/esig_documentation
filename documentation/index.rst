The ``esig`` Python Package
===========================

This is the online documentation for the Python ``esig`` package. Below you'll find the table of contents.

.. toctree::
   :maxdepth: 3
   
   about
   prerequisites
   installing
   troubleshooting

``esig``: What is it?
---------------------
The ``esig`` package provides implementations of a series of mathematical tools for the handling of the *signature* of a *path.* Powered by the underlying ``libalgebra`` C++ package, developed by Terry Lyons et al. over a period of 15 years, the ``esig`` package has been developed and extended by three 2017 Summer interns at the `Alan Turing Institute <http://www.turing.ac.uk/>`_, London, England. Below we provide an explanation of what a path and a signature are -- it gets mathematical.

Consider a *path* as a time evolving stream -- a continuous mapping from a time interval into some multidimensional space. A *signature* can be produced from a path, which is what ``esig`` primarily does -- as a mathematical object, a signature is an infinite vector. However, in practice, we work with truncated signatures to a certain *degree.*  Formally, each coordinate of the vector is an iterated Riemann-Stieltjes integral and represents an element in the tensor algebra of Euclidean space. For precise definitions, and an introduction to this particular research area, see `this article <https://arxiv.org/abs/1405.4537>`_ written by Terry Lyons, as well as `this survey paper <https://arxiv.org/abs/1602.03255>`_.

In practice, paths are easy to visualise as piecewise linear functions. The initial and end points as well as the intermediate breaking points are collected into an array, with the understanding that the data is linear in between the samples.

An example of sample input is a np.array of shape ``(l,n)`` where: ``l`` is the length of the path (+1); and ``n`` is the dimension of the target space. In the following example, the path is given as a list of coordinate vectors. Again, it is implicit that the path is linear inbetween.

.. code::
	
	(0,1) --> (1,1) --> (2,2) --> (3,0)

The signature is then computed by calling a degree, after formatting the data as a ``numpy.array``. The degree is roughly defined as the order to which iterated integration is performed. In this example, degree 3 means that all of the possible combinations of the coordinate functions

.. code::
	
	x_1 = (0 --> 1 --> 2 --> 3)
	x_2 = (1 --> 1 --> 2 --> 0)

of length 3 or lower are integrated over. There is 1 combination of length 0, 2 combinations of lenght 1, 4 combinations of length 2, 8 combinations of length 4, making the resulting vector have dimension 15.

Additionally, if you're interested in how the software was packaged up, you can look at the small reflection paper written by one of the Summer interns, David Maxwell. The paper is available for free on `arXiv <https://arxiv.org/>`_.

Who is Involved?
----------------
Over the Summer of 2017, a grade-A team were assembled at the Alan Turing Institute in London, England.

.. |terry| image:: images/terry.png
   :scale: 100%
   :align: middle
.. |hao| image:: images/hao.png
   :scale: 100%
   :align: top
.. |alex| image:: images/alexandru.png
   :scale: 100%
   :align: top
.. |radek| image:: images/radek.png
   :scale: 100%
   :align: top
.. |david| image:: images/david.png
   :scale: 100%
   :align: top

+---------+---------------------------------------+
| |terry| | | **Professor Terry Lyons**           |
|         | | Oxford-Man Institute                |
+---------+---------------------------------------+
| |hao|   | | **Dr Hao Ni**                       |
|         | | Senior Lecturer, UCL                |
+---------+---------------------------------------+
| |alex|  | | **Alexandru Cioba**                 |
|         | | PhD Student, UCL                    |
+---------+---------------------------------------+
| |radek| | | **Radoslaw Kowalski**               |
|         | | PhD Student, UCL                    |
+---------+---------------------------------------+
| |david| | | **David Maxwell**                   |
|         | | PhD Student, University of Glasgow  |
+---------+---------------------------------------+