.. _visualize_nao:

Visualizing Nao in RViz
-----------------------

Below are two sets of instructions, for using either:

* **A simulated robot (rcss3d_nao)** - with the `SimSpark`_ simulator using the `NaoSoccerSim`_ package
* **A real NAO (nao_lola)** - using the `Nao Lola`_ package

Select the appropriate tab.

.. tabs::

   .. group-tab:: rcss3d_nao

      These are instructions for visualizing a simulated robot.

      .. warning::
      
         Before continuing with this tutorial, make sure you have installed `SimSpark`_, `NaoSoccerSim`_, `ROS2 Nao Package`_,
         as well as the packages for this project. If you haven't yet, install them now.
 
      In a terminal, start the simulation server:

      .. code-block:: console
      
         rcsoccersim3d

      In a new terminal, run the simulated player node:
 
      .. code-block:: console

         ros2 run rcss3d_nao rcss3d_nao

      .. note::

         Simulated Nao publishes vision information as well as sensor information.
 
   .. group-tab:: nao_lola

      These are instructions for visualizing a real NAO.

      .. warning::
         
         Before continuing with this tutorial, make sure you have installed `Nao Lola`_,
         as well as the packages for this project.

      On the NAO, in a new terminal, start the nao_lola node:

      .. code-block:: console

         ros2 run nao_lola nao_lola

      .. note::

         nao_lola only publishes sensor information, you must run your own nodes that publish to vision topics.

In a new terminal, start the nao_state_publisher:

.. code-block:: console

   ros2 launch nao_state_publisher nao_state_publisher_launch.py

Finally, start rviz in a new terminal:

.. code-block:: console

   ros2 launch naosoccer_visualization_launch rviz_launch.py

Moving around in RViz, you should be able to see what the robot has observed.

.. image:: images/nao_rviz.png


.. _SimSpark: https://gitlab.com/robocup-sim/SimSpark/-/wikis/home
.. _NaoSoccerSim: https://naosoccer-sim.readthedocs.io/en/latest/index.html
.. _ROS2 Nao Package: https://ros2-nao.readthedocs.io/en/latest/index.html
.. _Nao Lola: https://nao-lola.readthedocs.io/en/latest/index.html