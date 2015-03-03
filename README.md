Cartridge for bpmPaaS with Travel Agency Demo
=============================================
This cartridge provides the **_Red Hat JBoss BPM Suite_** for easy deployment to OpenShift based bpmPaaS with pre-loaded Travel Agency Demo.


Install with one click in xPaaS (bpmPaaS)
-----------------------------------------
After clicking button, ensure `Gear` size is set to `medium`:

[![Click to install OpenShift](http://launch-shifter.rhcloud.com/launch/light/Install bpmPaaS.svg)](https://openshift.redhat.com/app/console/application_type/custom?&cartridges[]=https://raw.githubusercontent.com/npatel2012/cartridge-bpmPaaS-travel-agency-demo/master/metadata/manifest.yml&name=travelagency&gear_profile=medium&initial_git_url=)

Once installed you can use the JBoss BPM Suite logins: 

   * u:erics   p: bpmsuite  (admin)

   * u: alan   p: bpmsuite  (analyst)

   * u: daniel p: bpmsuite (developer)

   * u: ursla  p: bpmsuite (user)

   * u: mary   p: bpmsuite (manager)


Booking a trip to Edinburgh (just one scenario)
-----------------------------------------------
1. Build & deploy project.

2. Start process with following data in start form (either from JBoss BPM Suite dashboard or using external client
	 UI deployed at http://travelagency-${your-domain}.rhcloud.com:8080/external-client-ui-form-1.0

  ```
  Name: [your-name]

  Email Adress: [any-email]

  Number of Travellers: 2  

  From Destination: London

  To Destination: Edinburgh

  Preferred Date of Departure: 2014-12-20

  Preferred Data of Arrival: 2014-12-29

  Other Details / Notes: [any-text]
  ```

3. Login to http://travelagency-${your-domain}.rhcloud.com:8080/business-central

  ```
  - login for admin role (u:erics / p:bpmsuite1!)
  ```

4. Two web services will be run and a sub-process to calculate the cost before deciding it is not needed that this booking be
	 reviewed on pricing, so you will find a task 'Employee Booking' for you to process.

5. Navigate to the "Tasks" tab and click on it. From the task in the list, click on the "Lock" icon to claim the task

6. Click on the "Work" tab from the resulting right-side pane window that opened.

7. Fill in the form provided for the task, it allows review of all the booking data submitted, generated by services and 
   calculated by the rules. You can request a review to send it back for a pricing review or check the completed box to 
   finish the task and process (isBookingConfirmed).

8. Enter credit card details (beginning with 1234...) for compensation to be triggered., Expiry details of the 
   card (e.g. 12/12) and your full name.

9. Check the logs and you will see that the process has been compensated.

10. To trigger different path for successful booking of Flights, just change the 'Credit Card details' to use any 
    card number that does not begin with 1234....


Important Note
--------------
You need the ability to setup MEDIUM gears, which is freely available if you [upgrade your account to Bronze here] (https://www.openshift.com/products/pricing). 


Manual setup on OpenShift
-------------------------
Or if you want to use the [rhc command line](https://www.openshift.com/developers/rhc-client-tools-install) type:

    rhc app create -g medium <APP NAME> https://raw.githubusercontent.com/npatel2012/cartridge-bpmPaaS-travel-agency-demo/master/metadata/manifest.yml

For more information on the [JBoss BPM Travel Agency Demo see here] (https://github.com/npatel2012/bpms-travel-agency-demo).


Supporting Articles
-------------------
[Slides from webinar - How to excite the travel industry with a BPM story](http://www.schabell.org/2015/02/slides-webinar-jboss-bpm-travel-agency.html)

[Webinar - How to Excite the Travel Industry with a BPM Story](http://www.schabell.org/2015/02/webinar-how-to-excite-travel-industry.html)

[Quickest Way into the Clouds with JBoss BPM Travel Agency](http://www.schabell.org/2015/02/into-clouds-with-jboss-bpm-travel-agency.html)

[How to fly with the JBoss BPM Travel Agency (video 4 of 4)](http://www.schabell.org/2015/02/how-to-fly-with-jboss-bpm-travel-agency-part4.html)

[How to fly with the JBoss BPM Travel Agency (video 3 of 4)](http://www.schabell.org/2015/01/how-to-fly-with-jboss-bpm-travel-agency-part3.html)

[How to fly with the JBoss BPM Travel Agency (video 2 of 4)](http://www.schabell.org/2015/01/how-to-fly-with-jboss-bpm-travel-agency-part2.html)

[How to Fly with the JBoss BPM Travel Agency (video 1 of4)](http://www.schabell.org/2015/01/how-to-fly-with-jboss-bpm-travel-agency.html)

[3 Reasons You Need The New JBoss Travel Agency](http://www.schabell.org/2014/12/3-reasons-you-need-new-jboss-travel-agency.html)

[How To Excite the Travel Industry With a BPM Story](http://www.schabell.org/2014/10/how-to-excite-travel-agencies-with-bpm-story.html)


Released versions
-----------------
See the tagged releases for the following versions of the product:

- v1.0 - bpmPaaS on OpenShift cartridge, JBoss BPM Suite 6.0.2 and JBoss BPM Travel Agency demo installed.


![Digital Sign Annoucement](https://github.com/npatel2012/bpms-travel-agency-demo/blob/master/docs/demo-images/cloud-sign.jpg?raw=true)

