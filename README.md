## OBJECTIVE 
This robot will book a flight and handle the calendar (Chick-in and Chick-out) Date.
Recognize [data format microsoft](https://learn.microsoft.com/en-us/system-center/orchestrator/standard-activities/format-date-time?view=sc-orch-2022)
## TECHNICAL REQUIREMENTS
  ###  While Activity
1) [While Actvity](https://docs.uipath.com/activities/other/latest/workflow/interruptible-while)
## PROCEDURES
1) Use Browser Chrome: Booking.com > Input Dialog

   ![image](https://github.com/user-attachments/assets/87bffa83-7779-421a-a872-9d8ed725a42d)

3) Type into > Click


   ![image](https://github.com/user-attachments/assets/d2e69a79-830d-4505-8e2d-e8bd2795fc71)


4) Get text, In order to send the current month > Message Box

   ![image](https://github.com/user-attachments/assets/2ed1a200-d48a-4a3d-9b40-b8e6229bbb66)


5) Input Dialog, To ask the user when to book a flight

    ![image](https://github.com/user-attachments/assets/415bb8e3-e4aa-44ab-9120-fea1af38cc07)



* Based on Date/Time Format Codes

  
    ![image](https://github.com/user-attachments/assets/c5def0d2-54f7-423d-842a-c692673405e6)

6) Multiple Assign > Message Box

   * strMonthYear : A variable containing the month in word form and the year in number form
   * strDayOnly : l It will only store the day of the entered date
  
     
    ![image](https://github.com/user-attachments/assets/3b0cfd27-916c-47cd-b84f-3fa413228db4)

   * In side Value(In Argument) field :DateTime.ParseExact(checkInDate,"d/MM/yyyy",system.Globalization.CultureInfo.InvariantCulture).ToString("MMMM yyyy")
   *  In side Value(In Argument) field : DateTime.ParseExact(checkInDate,"d/MM/yyyy",system.Globalization.CultureInfo.InvariantCulture).ToString("d/MM").Split("/")(0)
  
7) While
   * Condition: CurreentMonthOnCalender.Trim<>strMonthYear.Trim

     ![image](https://github.com/user-attachments/assets/eb3a00ff-c259-4e74-b00b-ff9bf1a6dcf8)

     ![image](https://github.com/user-attachments/assets/d8c98bb9-b17c-4f00-beed-3902177b7097)

8) The while function is to search for the month only. Once it is found, the loop will be exited and click will be used to find the desired day.

    ![image](https://github.com/user-attachments/assets/c014010c-e697-4073-b36f-5df4d9d456c0)

   * In order to change the day to suit the user


  <img src="https://github.com/user-attachments/assets/eac880ab-9b9e-47d7-b7a5-9c69fc9fcdb8" width="200">
  



  .
   <img src="https://github.com/user-attachments/assets/5dbcb384-3e9b-45a5-8fb4-7e8c4ce3c292" width="200">
  
 




## Results

To watch the First Bot run this video, [click here](https://drive.google.com/file/d/17Gcr1kf5O3nFBrIgxTIWEqgkTvOI4CYt/view?usp=drive_link)
