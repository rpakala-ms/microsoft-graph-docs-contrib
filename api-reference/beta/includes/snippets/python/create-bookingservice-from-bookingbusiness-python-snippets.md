---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(request_adapter)

request_body = BookingService(
	odata_type = "#microsoft.graph.bookingService",
	default_duration = "PT1H30M",
	default_location = Location(
		odata_type = "#microsoft.graph.location",
		address = PhysicalAddress(
			odata_type = "#microsoft.graph.physicalAddress",
			city = "Buffalo",
			country_or_region = "USA",
			postal_code = "98052",
			post_office_box = None,
			state = "NY",
			street = "4567 First Street",
			type = None,
			additional_data = {
					"type@odata_type" : "#microsoft.graph.physicalAddressType",
			}
		),
		coordinates = None,
		display_name = "Contoso Lunch Delivery",
		location_email_address = None,
		location_type = None,
		location_uri = None,
		unique_id = None,
		unique_id_type = None,
		additional_data = {
				"location_type@odata_type" : "#microsoft.graph.locationType",
				"unique_id_type@odata_type" : "#microsoft.graph.locationUniqueIdType",
		}
	),
	default_price = 10,
	default_price_type = BookingPriceType.FixedPrice,
	default_reminders = [
		BookingReminder(
			odata_type = "#microsoft.graph.bookingReminder",
			message = "Please be reminded that this service is tomorrow.",
			offset = "P1D",
			recipients = BookingReminderRecipients.AllAttendees,
			additional_data = {
					"recipients@odata_type" : "#microsoft.graph.bookingReminderRecipients",
			}
		),
	]
	description = "Individual bento box lunch delivery",
	display_name = "Bento",
	is_location_online = True,
	sms_notifications_enabled = True,
	language_tag = "en-US",
	is_hidden_from_customers = False,
	notes = "Home-cooked special",
	post_buffer = "PT10M",
	pre_buffer = "PT5M",
	scheduling_policy = BookingSchedulingPolicy(
		odata_type = "#microsoft.graph.bookingSchedulingPolicy",
		allow_staff_selection = True,
		maximum_advance = "P10D",
		minimum_lead_time = "PT10H",
		send_confirmations_to_owner = True,
		time_slot_interval = "PT1H",
	),
	staff_member_ids = [
		"d90d1e8c-5cfe-48cf-a2d5-966267375b6a",
		"2f5f8794-0b29-45b5-b56a-2eb5ff7aa880",
	]
	is_anonymous_join_enabled = False,
	additional_data = {
			"default_price_type@odata_type" : "#microsoft.graph.bookingPriceType",
			"default_reminders@odata_type" : "#Collection(microsoft.graph.bookingReminder)",
			"staff_member_ids@odata_type" : "#Collection(String)",
	}
)

result = await graph_client.booking_businesses.by_booking_businesse_id('bookingBusiness-id').services.post(body = request_body)


```