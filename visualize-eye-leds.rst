Visualizing eye leds in RViz
############################

Opening Eye LEDs Panel in RViz
******************************

.. image:: images/eye-leds-panel.gif

.. note::

  Instructions here assume you have installed and sourced the packages for this project.

In a new terminal, open rviz2:

.. code-block:: console
  
  rviz2
  
From the menu bar, select **Panels > Add New Panel**
Select **Eye LEDs Panel**, under **naosoccer_rviz_plugins**.
You should see the plugin show up.

.. tip::

  If you don't see the plugin show up in the list, you probably forgot to run
  `. install/local_setup.sh` in your workspace after building the packages.

Visualizing LED Commands
************************

.. important::

  **The original rqt_publisher has a bug** that doesn't allow publishing arrays. To get around this,
  we build a patched version of rqt_publisher. In your workspace directory, run:

  .. code-block:: console

    git clone -b foxy-devel https://github.com/ijnek/rqt_publisher.git src/rqt_publisher
    colcon build
    source install/local_setup.bash

  There is a pending PR for this patch into the main repository.

.. image:: images/publish-eye-leds.gif

In a new terminal, open rqt's publisher plugin:

.. code-block:: console

  rqt -s rqt_publisher.publisher.Publisher

From **topic**, select **/effectors/left_eye_leds** (or /effectors/right_eye_leds) and click the **+ button** to add a publisher.

Modify the r, g, b values between 0.0 and 1.0, for each LED. You should see the LEDs change color in rviz.

.. seealso::

  `nao_command_msgs/msg/LeftEyeLeds`_ and `nao_command_msgs/msg/RightEyeLeds`_ for more details, such as the led locations.


.. _nao_command_msgs/msg/LeftEyeLeds: https://nao-interfaces-docs.readthedocs.io/en/latest/leds.html#left-eye-leds
.. _nao_command_msgs/msg/RightEyeLeds: https://nao-interfaces-docs.readthedocs.io/en/latest/leds.html#right-eye-leds