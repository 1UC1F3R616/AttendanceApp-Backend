""" To help someone who will work on this in future, To help the frontend person: (This may not be exactly True)

when a new event is created, event-name (slug) is added in events db. Now when attende sends otp we take it and check if it matches with any
event and event attendence is going on. Then we take attendence and emit this info to admin namespace.
also, attende attendence is sended to one more route that attendence is emited to that particular event room (if allowed for so by admin).

attendence is emitted to:
1) attendence namespace, from their attendence is done and emited to admin.
2) broadcaster namespace, from there to specific room name if allowed by admin.

admin_namespace -> to emit to the admin_namespace :emits to the client side namespace then  (SERVER SIDE NOT NEEDED)
attendence_namespace-> attendence (to emit client attendence) :emits to the client side admin_namespace then
broadcaster_namespace -> attendence comes to this namespace also, from here it's sended to particular room """



#### To be continued

# Create API endpoints for admin to mark someones attendence
# Endpoint to generate csv file for a paticular event with attendes details
# Time check, before attendence verify it's in allowed time limit. Or frontend takes care of this and don't send vague requests \
#or server takes request don't add to db and sends a message Attendence is closed now.
#fetch creation_date and time_delta then before adding see if valid.
# An API to give a few otp examples which are available


##### To be done
# so much cleaning and filtering and purifying
# use bcrypt to genrate and store passwords in hashes only-
    # signup, create and commit in database
    # login, check
# make use of make_response, to add status code as well along with jsonify return

# from passlib.hash import pbkdf2_sha256 as sha256
# jwt token expiry thing api


# In Events table, admin name is used, can be either made unique during /
#registration or make it admin email. Ask?
# add field admin_email in events model
# add admin_email field in sockets attendence_namespace payLoad for admin

## model changes
# add field admin_email in events model

## Not doing (left for future if someone works):
# replace flask-jwt with flask-jwt-extended
# empty password is allowed :) Yes, Auth is just to keep users track
# only single ip connection allowed for 1 user
# clean datetime.datetime.now()
# check bugs for sockets