.. _visualize_nao:

Visualizing Nao in RViz
-----------------------

.. note::
   
   This tutorial assumes you have installed `SimSpark`_, `NaoSoccerSim`_, `ROS2 Nao Package`_,
   as well as this package.


To visualize the robot in RViz, do the following, in separate terminals.

Start the simulation server:

.. code-block:: console

   rcsoccersim3d

Start our simulated player:

.. code-block:: console

   ros2 launch rcss3d_agent player_launch.py

Start our nao_state_publisher:

.. code-block:: console

   ros2 launch nao_state_publisher nao_state_publisher_launch.py

Finally, start rviz:

.. code-block:: console

   ros2 launch naosoccer_visualization rviz_launch.py

Moving around in RViz, you should be able to see **the robot and the ball** it has observed.

.. image:: images/nao_rviz.png


.. _SimSpark: https://gitlab.com/robocup-sim/SimSpark/-/wikis/home
.. _NaoSoccerSim: https://github.com/ijnek/naosoccer_sim
.. _ROS2 Nao Package: https://github.com/ijnek/nao