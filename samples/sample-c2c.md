## variables
#set($feature_fare=$fare)
#set ($source = "&source=nl_bb-route")
#set($bgcolor="#f6f6f6")
#set($bghottip="#F68018")
#set($font-family="arial")
#set($font-color-black="#282828")
#set($font-color-white="#FFFFFF")
#set($font-color-orange="#F68018")
#set($contentbgcolor="#ffffff")
#set($border-spec="1px #DADADA solid")
#set($image_basic_url="http://i.slimg.com/htmlemail/bb/c2c/c2c-141505/")
#set($airline_icon="Airlines_Icon.png")
#set($read_more_image="DesktopB_ReadMore_btn.png")
#set($see_hotel_btn_desktop="DesktopB_SeeHotel_btn.png")
#set($see_hotel_btn_mobile="MobileB_SeeHotel_btn.png")
#set($see_details_btn_desktop="DesktopB_SeeDetails_btn.png")
#set($feature_fare_see_details="DesktopB_SeeDetailsTop_btn.png")
#set($search_widget_1="Widget_01.png")
#set($search_widget_2="Widget_02.png")
#set($search_widget_3="Widget_03.png")
#if (${hot_tip} && ${hot_tip.image_url} != "" && $is_engaged == "true")
	#set ($subject = "${feature_fare.departureAirportCode} ➔ ${feature_fare.arrivalAirportCode} ${feature_fare.priceFormatted} + | ${hot_tip.title}")
#else 
	#set ($subject = "Alert: ${dep_city_name_short} ➔ ${arr_city_name_short} ${feature_fare.priceFormatted}+ RT")
#end
## Hot Tips
#if (${hot_tip})
	#set($hot_tip_image_url=${hot_tip.image_url})
	#set($hot_tip_image_alt=${hot_tip.image_alt})
	#set($hot_tip_summary=${hot_tip.summary})
	#set($hot_tip_title=${hot_tip.title})
	#set($hot_tip_url=${hot_tip.url})
#else
	#set($hot_tip_title="")
#end
## Feature fare
#if ($feature_fare)
	#set($feature_fare_destination=${arr_city_name_short})
	#set($feature_fare_destination_code=${feature_fare.arrivalAirportCode})
	#set($feature_fare_departure_code=${feature_fare.departureAirportCode})
	#set($feature_fare_departure=${dep_city_name_short})
	#set($feature_fare_price=${feature_fare.priceFormatted})
	#set($feature_fare_flight_type=${feature_fare.flightType})
	#set($feature_fare_image_url=${feature_fare_image})
	#set($feature_fare_airlinetext=${feature_fare.airlinesText})
	#set($feature_fare_url=${feature_fare.airlinesText})
	#set($feature_fare_id=${feature_fare.fareId})
#else
	#set($feature_fare_destination="")
#end
## macro for hot tip
#macro(macro_hot_tip, $hot_tip_title, $hot_tip_url, $hot_tip_image_url ,$hot_tip_image_alt, $hot_tip_title, $read_more_image)
	#if($hot_tip_title != "" && $hot_tip_image_url != "")
		<!-- hot tip title -->
		<tr>
			<td width="100%" heidth="35" style="width:100%; height:35px;">
				<table width="390" align="left" style="width:390px;" border="0" align="left" cellpadding="0" cellspacing="0" >
					<tbody>
						<tr>
							<td width="100%" height="35" bgcolor="$font-color-orange" align="left" style="width: 100%; height:35px; font-family: $font-family; color: $font-color-white; font-size: 20px; padding-left: 5px;">
								Hottest Tips in Travel
							</td>
						</tr>
					</tbody>
				</table>
			</td>
		</tr>
		<!-- hot tip content containter -->
		<tr>
			<td width="100%" height="150" align="left" bgcolor="#ffffff" style="width: 100%; height:150px;bgcolor:#ffffff; border: $border-spec;">
				<!-- image -->
				<table width="228" height="150" border="0" align="left" cellpadding="0" cellspacing="0" style="width:228px; height:150px;">
					<tbody>
						<tr>
							<td align="center" width="228" height="150" style="width:228px; height:150px;">
								<a href=$hot_tip_url style="text-decoration:none;" target="_blank">
									<img src=$hot_tip_image_url  alt=$hot_tip_image_alt width="228" height="150" border="0" style="display:block; width:228px; height: 150px;">
								</a>
							</td>
						</tr>
					</tbody>
				</table>
				<!-- horizontal spacing -->
				<table width="10" cellspacing="0" cellpadding="0" border="0" align="left" style="width:10px;">
					<tbody>
						<tr>
							<td width="10" height="10" style="font-size: 1px; line-height: 1px;">&nbsp;</td>
						</tr>
					</tbody>
				</table>
				<!-- content -->
				<table border="0" class="w235" width="255" height="150" align="left" cellpadding="0" cellspacing="0">
					<tbody>
						<!-- vertical spacing -->
						<tr>
							<td width="100%" height="10" style="font-size: 1px; line-height: 10px;"></td>
						</tr>
						<tr>
							<td  align="left" width="200" height="30" style="width: 200px;height:30px; font-family: $font-family; color: $font-color-black; font-size: 18px;">
								<a href="$hot_tip_url" style="text-decoration:none;" target="_blank">
									<span style="font-family: $font-family; color: $font-color-black; font-size: 18px;">$hot_tip_title</span>
								</a>
								
							</td>
						</tr>
						<tr>
							<td  align="left" width="200" height="15" style="width: 200px;height:15px; font-family: $font-family; color: #777777; font-size: 13px;">
								<a href="$hot_tip_url" style="text-decoration:none;" target="_blank">
									<span style="font-family: $font-family; color: #777777; font-size: 13px;">Source: SmarterTravel</span>
								</a>
							</td>
						</tr>
						<!-- vertical spacing -->
						<tr>
							<td width="100%" height="10" style="height:10px;font-size: 1px; line-height: 10px;">&nbsp;</td>
						</tr>
						<!-- "Read More" button -->
						<tr>
							<td  align="left" class="w125 h40" width="115" height="35">
								<a href=$hot_tip_url style="text-decoration:none;" target="_blank">
									<img src=$image_basic_url/$read_more_image  alt="" class="w125 h40" width="115" height="35" border="0" style="display:block; width:115px; height: 35px;">
								</a>
							</td>
						</tr>
					</tbody>
				</table>
			</td>
		</tr>
		<!-- vertical spacing -->
		<tr>
			<td class="h40" width="100%" height="50" style="font-size: 1px; line-height: 10px;"></td>
		</tr>
	#end
#end
## macro for feature fare
#macro(macro_feature_fare, $feature_fare_title, $feature_fare_departure, $feature_fare_destination, $feature_fare_price , $feature_fare_flight_type, $feature_fare_flight_type, $feature_fare_airlinetext, $feature_fare_image_url, $feature_fare_destination_code)
	#if($feature_fare_title != "")
		<!-- feature fare title -->
		<tr>
			<td width="100%" heidth="35" style="width:100%; height:35px;">
				<table width="390" align="left" style="width:390px;" border="0" align="left" cellpadding="0" cellspacing="0" >
					<tbody>
						<tr>
							<td width="100%" height="35" bgcolor="#3baed5" align="left" style="width: 100%; height:35px; font-family: $font-family; color: $font-color-white; font-size: 20px; padding-left: 5px;">
								Top Deal! $feature_fare_departure to $feature_fare_destination
							</td>
						</tr>
					</tbody>
				</table>
			</td>
		</tr>
		<!-- feature fare content -->
		<tr>
			<td width="100%" height="90" align="left" bgcolor="#ffffff" style="width: 100%; height:90px;bgcolor:#ffffff; border-top: $border-spec; border-left: $border-spec; border-right: $border-spec;">
				<!-- horizontal spacing -->
				<table width="10" cellspacing="0" cellpadding="0" border="0" align="left" style="width:10px;">
					<tbody>
						<tr>
							<td width="20" height="20" style="font-size: 1px; line-height: 1px;">&nbsp;</td>
						</tr>
					</tbody>
				</table>
				<!-- content -->
				<table border="0" class="" width="460" height="90" align="left" cellpadding="0" cellspacing="0">
					<tbody>
						<!-- vertical spacing -->
						<tr>
							<td width="100%" height="20" style="font-size: 1px; line-height: 10px;"></td>
						</tr>
						<tr>
							<td  align="left" width="480" height="40" style="width: 480px; height:40px;">
								<!-- price | destination | airline text -->
								<table width="300" cellspacing="0" cellpadding="0" border="0" align="left" style="width: 300px;" >
									<tbody>
										<!-- price | destination -->
										<tr>
											<td width="100" style="width: 100%;">
												<a href="http://rd.bookingbuddy.com/?r=i3993194n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&fare_id=$feature_fare_id&departure_city=$feature_fare_departure_code&arrival_city=$feature_fare_destination_code${source}_featfare_${nl_date_numeric}&ns=1" style="text-decoration:none;" target="_blank">
													<span style="font-family: $font-family; font-size: 30px; color:$font-color-black">$feature_fare_price 
														<span style="font-family: $font-family; font-size: 16px; color:$font-color-black">$feature_fare_flight_type</span>  <span style="color:#777; font-size: 25px;">|</span> </span> 
												</a>
												<span style="font-family: $font-family; font-size: 18px; color:$font-color-black">$feature_fare_destination</span>
											</td>
										</tr>
									</tbody>
								</table>
								<!-- "See Detail" -->
								<table cellspacing="0" cellpadding="0" border="0" align="right">
									<tbody>
										<tr>
											<td width="125" height="40" border="0" style="width:125px; height: 40px;">
												<a href="http://rd.bookingbuddy.com/?r=i3993194n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&fare_id=$feature_fare_id&departure_city=$feature_fare_departure_code&arrival_city=$feature_fare_destination_code${source}_featfare_${nl_date_numeric}&ns=1" style="text-decoration:none;" target="_blank">
													<img src=$image_basic_url/$feature_fare_see_details alt="" class="" width="125" height="40" border="0" style="display:block; width:125px; height: 40px;">
												</a>
											</td>
										</tr>
									</tbody>
								</table>
							</td>
						</tr>
						<!-- vertical spacing -->
						<tr >
							<td width="100%" style="width:100%; max-height: auto;">
								<!-- airline text for mobile only -->
								<table width="30" style=" height: 12px;  width:30px;"  cellspacing="0" cellpadding="0" border="0" align="left" >
									<tbody>
										<tr>
											<td width="30" height="12" border="0" style="width:30px; height: 12px;">
												<img src=$image_basic_url/$airline_icon alt="" width="30" height="12" border="0" style="height: 12px;width: 30px">
											</td>
										</tr>
									</tbody>
								</table>
								<!-- horizontal spacing -->
								<table width="5"  cellspacing="0" cellpadding="0" border="0" align="left" style="width:5px; height: 12px; ">
									<tbody>
										<tr>
											<td width="5" height="5" style="font-size: 1px; line-height: 1px;">&nbsp;</td>
										</tr>
									</tbody>
								</table>
								<table cellspacing="0" cellpadding="0" border="0" align="left">
									<tbody>
										<tr>
											<td style="font-size: 13px; line-height: 1;font-family: $font-family;color: #777;">
												$feature_fare_airlinetext
											</td>
										</tr>
									</tbody>
								</table>
							</td>
						</tr>
						<!-- vertical spacing -->
						<tr>
							<td width="100%" height="10" style="height:10px;font-size: 1px; line-height: 10px;">&nbsp;</td>
						</tr>
					</tbody>
				</table>
			</td>
		</tr>
		<!-- feature fare image -->
		<tr>
			<td class="wAll h320" align="left" class="" width="500" height="333">
				<a href="http://rd.bookingbuddy.com/?r=i3993194n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&fare_id=$feature_fare_id&departure_city=$feature_fare_departure_code&arrival_city=$feature_fare_destination_code${source}_featfare_${nl_date_numeric}&ns=1" style="text-decoration:none;" target="_blank">
					<img src=$feature_fare_image_url  alt="" class="wAll h320" width="500" height="333" border="0" style="display:block; width:500px; height: 333px;">
				</a>
			</td>
		</tr>
		<!-- vertical spacing -->
		<tr>
			<td width="100%" height="5" style="font-size: 1px; line-height: 10px;">&nbsp;</td>
		</tr>
		<!-- feature fare footer -->
		<tr>
			<td  width="100%" style="font-family: $font-family; font-size: 13px; color: $font-color-black">
				No longer interested in travel to $feature_fare_destination ($feature_fare_destination_code)? 
				<a href="http://rd.bookingbuddy.com/?r=i3961415n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&email=${email_encoded}&mode=prefs${source}" style="text-decoration:none;" target="_blank"><span  style="font-family: $font-family; font-size: 13px; color:#26A6D1; border-bottom: 1px solid #26A6D1; border-bottom: 1px solid #26A6D1">Update your route</span></a>
			</td>
		</tr>
		<!-- vertical spacing -->
		<tr>
			<td class="h40" width="100%" height="50" style="font-size: 1px; line-height: 10px;"></td>
		</tr>
	#end
#end
## macro for nearby fares
#macro(macro_nearby_fares, $nearby_fares)
	#if ($nearby_fares && $nearby_fares.size() > 0)
		<!-- nearby fare title -->
		<tr>
			<td width="100%" heidth="35" style="width:100%; height:35px;">
				<table width="390" align="left" style="width:390px;" border="0" align="left" cellpadding="0" cellspacing="0" >
					<tbody>
						<tr>
							<td  width="100%" bgcolor="#3baed5" align="left" style="width: 100%; height:35px; font-family: $font-family; color: $font-color-white; font-size: 20px; padding-left: 5px;">
								Lower Fares to $feature_fare_destination from
							</td>
						</tr>
					</tbody>
				</table>
			</td>
		</tr>
		<!-- for desktop -->
		#foreach ($fare in $nearby_fares)
			<tr>
				<td width="100%" height="60" align="left" bgcolor="#ffffff" style="width: 100%; height:60px; bgcolor:#ffffff; border-top: $border-spec;">
					<!-- horizonal spacing -->
					<table width="10" cellspacing="0" cellpadding="0" border="0" align="left" style="width:10px;">
						<tbody>
							<tr>
								<td width="10" height="10" style="font-size: 1px; line-height: 1px;">&nbsp;</td>
							</tr>
						</tbody>
					</table>
					<!-- destination city -->
					<table width="170" height="60" cellspacing="0" cellpadding="0" border="0"  align="left" style="width:170px; height: 60px;">
						<tbody>
							<tr>
								<td width="170" height="60"  style="width: 170px; height: 60px;">
									<a href="http://rd.bookingbuddy.com/?r=i3993194n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&fare_id=$fare.fareId&departure_city=$fare.departureAirportCode&arrival_city=$fare.arrivalAirportCode${source}_listfare_$fare.departureAirportCode&ns=1" style="text-decoration:none;" target="_blank">
										<span style="font-family: $font-family; font-size: 17px; color:$font-color-black">$fare.departureAirportDisplay</span>
									</a>
								</td>
							</tr>
						</tbody>
					</table>
					<!-- fare price-->
					<table class="w150" width="175" height="60" cellspacing="0" cellpadding="0" border="0" align="left" style="width: 175px; height:60px; " >
						<tbody>
							<!-- price | destination -->
							<tr>
								<td width="100%" height="60" style="width: 100%; height: 60px; ">
									<a href="http://rd.bookingbuddy.com/?r=i3993194n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&fare_id=$fare.fareId&departure_city=$fare.departureAirportCode&arrival_city=$fare.arrivalAirportCode${source}_listfare_$fare.departureAirportCode&ns=1" style="text-decoration:none;" target="_blank">
										<span style="font-family: $font-family; font-size: 30px; color:$font-color-black">$fare.priceFormatted 
											<span style="font-family: $font-family; font-size: 16px; color:$font-color-black">$fare.flightType</span></span>
									</a>
								</td>
							</tr>
						</tbody>
					</table>
					<!-- "See Detail" -->
					<table width="125" height="60" cellspacing="0" cellpadding="0" border="0" align="left" style="height: 60px;">
						<tbody>
							<tr>
								<td width="125" height="60" border="0" style="width:125px; height: 60px;">
									<a href="http://rd.bookingbuddy.com/?r=i3993194n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&fare_id=$fare.fareId&departure_city=$fare.departureAirportCode&arrival_city=$fare.arrivalAirportCode${source}_listfare_$fare.departureAirportCode&ns=1" style="text-decoration:none;" target="_blank">
										<img src=$image_basic_url/DesktopB_SeeDetails_btn.png alt="" class="" width="125" height="30" border="0" style="display:block; width:125px; height: 30px;">
									</a>
								</td>
							</tr>
						</tbody>
					</table>
				</td>
			</tr>
		#end
		<!-- vertical spacing -->
		<tr>
			<td width="100%" height="10" style="font-size: 1px; line-height: 10px;"></td>
		</tr>
		<tr>
			<td width="100%" height="15" align="left" style="width:100%; height:15px;">
				<table class="mobileShow" style="display: none; line-height: 0; font-size:0px; max-height: 0px;" align="left" cellspacing="0" cellpadding="0" border="0" >
					<tbody>
						<tr class="mobileShow-wAll-h15-f13" style="font:0;">
							<td class="mobileShow-wAll-h15-f13" width="0" style=" width:0px; height:15px; max-height: 0; font-family: $font-family; font-size: 0px; color:$font-color-black;  ">
								All fares shown are round trip.
							</td>
						</tr>
					</tbody>
				</table>
				<table class="mobileShow-right" align="left" cellspacing="0" cellpadding="0" border="0" >
					<tbody>
						<tr>
							<td width="100%" align="right" height="15" style="width:100%; height:15px;">
								<a href="http://rd.bookingbuddy.com/?r=i3993200n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&departure_city=${feature_fare.departureAirportCode}" style="text-decoration:none;" target="_blank">
									<span style="font-family: $font-family; font-size: 13px; color:#26A6D1; border-bottom: 1px solid #26A6D1;">See more flights from ${dep_city_name_short}</span>
								</a>
							</td>
						</tr>
					</tbody>
				</table>
			</td>
		</tr>	
		<!-- for mobile -->
	#end
	<!-- vertical spacing -->
	<tr>
		<td class="h40" width="100%" height="50" style="font-size: 1px; line-height: 10px;"></td>
	</tr>
#end
## macro for hotel deal item on mobile
#macro(macro_hotel_deal, $deal)
	#set($destination_id = $deal.DestinationID)
	<table class="w480 h155" width="243" height="auto" align="left" cellspacing="0" cellpadding="0" border="0" style="width: 243px; height:auto;">
		<tbody>
			<tr>
				<td class="w233 h155 mobileShow-table-cell" width="243" height="315" style="width: 243px; height:315px; display:block;" valign="top">
					<!-- image -->
					#if ($deal.ImageURL != "")
					<table class="w233 h155" width="243" height="163" align="left" cellspacing="0" cellpadding="0" border="0" style="width: 243px; height:163px;">
						<tr>
							<td>
								<a href="http://rd.BookingBuddy.com/?r=i7250204n$newsletter_id}&u=${tracking_code}&nltv=${nltv}&tid=$deal.HotelID&did=$deal.DestinationID" style="text-decoration:none;" target="_blank">
									<img class="w233 h155"  width="243" height="163" src=$deal.ImageURL  alt=""  border="0"  style="width: 243px; height:163px;"/>
								</a>
							</td>
						</tr>
					</table>
					#end
					<!-- main content -->
					<table class="w247 h155" width="243" height="155" align="left" cellspacing="0" cellpadding="0" border="0" bgcolor="#ffffff" style="width: 243; height:155px; display:block; ">
						<tbody>
							<!-- hotel name -->
							<tr>
								<td height="25" align="center" width="243" colspan="0" style="width: 243px; height: 25px; font-family: $font-family; font-size: 18px; padding-top: 10px; color: $font-color-black; ">
									<a href="http://rd.BookingBuddy.com/?r=i7250204n$newsletter_id}&u=${tracking_code}&nltv=${nltv}&tid=$deal.HotelID&did=$deal.DestinationID" style="text-decoration:none;" target="_blank">
									<span style="font-family: $font-family; font-size: 18px; padding-top: 10px; color: $font-color-black; ">$deal.Hotel.Name</span>
									</a>
								</td>
							</tr>
							<!-- price -->
							<tr>
								<td  height="30" align="center" width="243" colspan="0" style="width:243px; height:30px; font-family: $font-family; font-size: 28px; color: $font-color-black; padding-bottom: 10px; padding-top: 10px;">
									<a href="http://rd.BookingBuddy.com/?r=i7250204n$newsletter_id}&u=${tracking_code}&nltv=${nltv}&tid=$deal.HotelID&did=$deal.DestinationID" style="text-decoration:none;" target="_blank">
										<span style="font-family: $font-family; font-size: 28px; color: $font-color-black;">$deal.Price +</span>
									</a>
								</td>
							</tr>
							<!-- "see hotel" btn -->
							<tr>
								<td width="100%" height="40" colspan="0" align="left" style=" width:100%; height: 40px;">
									<table width="60" height="5" cellspacing="0" cellpadding="0" border="0" align="left" style=" width:60px; height:5px; " >
										<tr>
											<td width="60" height="5" align="left" style=" width:60px; height:5px;">&nbsp;</td>
										</tr>
									</table>
									<table width="130" height="40" cellspacing="0" cellpadding="0" border="0" align="left" style="width:130px; height:40px;" >
										<tr>
											<td width="130" height="40" align="left" style=" width:130px; height:40px;">
												<a href="http://rd.BookingBuddy.com/?r=i7250204n$newsletter_id}&u=${tracking_code}&nltv=${nltv}&tid=$deal.HotelID&did=$deal.DestinationID" style="text-decoration:none;" target="_blank">
													<img src=$image_basic_url/$see_hotel_btn_mobile  alt="" class="" width="130" border="0" style=" width:130px; height:40px;">
												</a>
											</td>
										</tr>
									</table>
								</td>
							</tr>
							<!-- vertical spacing -->
							<tr>
								<td class="" width="100%" height="10" style="font-size: 1px; line-height: 10px;"></td>
							</tr>
						</tbody>
					</table>
				</td>
			</tr>
			<!-- vertical spacing -->
			<tr>
				<td class="" width="100%" height="10" style="font-size: 1px; line-height: 10px;"></td>
			</tr>
		</tbody>
	</table>
#end
#macro(macro_hotel_deals, $deals)
	## The min number of the deals is 2 and the max one is 4
	#if ($deals && $deals.size() >= 2)
		<!-- Popular Hotel Title -->
		<tr>
			<td>
				<table width="390" align="left" style="width: 390px;" border="0" align="left" cellpadding="0" cellspacing="0" >
					<tbody>
						<tr >
							<td class="mobileShow-w390-h35-f20-lp5" width="0"  bgcolor="#96bd4f" align="left" style="width: 390px; height:35px; font-family: $font-family; color: $font-color-white; font-size: 20px; padding-left: 5px; ">
								Popular Hotel Deals in ${arr_city_name_short}
							</td>
						</tr>
					</tbody>
				</table>
			</td>
		</tr>
		## When there are two or three deals, only show two
		#if ($deals.size() < 4)
			##There are less than four deals, show the two in one row
			<tr>	
				<td class="w480" width="500" style="width:500px;">
				#set($count = 0)
				#foreach ($deal in $deals)
					#if ($count < 2)
						#macro_hotel_deal($deal)
						#if ($count == 0 )
							<table class="mobileHide" width="5" height="5" cellspacing="0" cellpadding="0" border="0" align="left" style="width:5px; height:5px;" >
								<tr>
									<td class="mobileHide"  width="5" height="5" align="left" style="font-size: 1px; line-height: 1px;">&nbsp;</td>
								</tr>
							</table>
						#end
					#end
					#set($count = $count + 1)
				#end
				</td>
			</tr>
		#else
			<!-- Row 1 -->
			## When there are four deals in total
			<tr>	
				<td class="w480" width="500" style="width:500px;">
				#set($count = 0)
				#foreach ($deal in $deals)
					#if ($count < 2)
						#macro_hotel_deal($deal)
						#if ($count == 0 )
							<table class="mobileHide" width="5" height="5" cellspacing="0" cellpadding="0" border="0" align="left" style="width:5px; height:5px;" >
								<tr>
									<td class="mobileHide"  width="5" height="5" align="left" style="font-size: 1px; line-height: 1px;">&nbsp;</td>
								</tr>
							</table>
						#end
						#set($count = $count + 1)
					#end
				#end
				</td>
			</tr>
			<!-- Row 2 -->
			<tr>	
				<td class="w480" width="250" style="width:250px;">
				#set($count = 0)
				#foreach ($deal in $deals)
					#if ($count >= 2)
						#macro_hotel_deal($deal)
						#if ($count == 2 )
							<table class="mobileHide" width="5" height="5" cellspacing="0" cellpadding="0" border="0" align="left" style="width:5px; height:5px;" >
								<tr>
									<td class="mobileHide"  width="5" height="5" align="left" style="font-size: 1px; line-height: 1px;">&nbsp;</td>
								</tr>
							</table>
						#end
					#end
					#set($count = $count + 1)
				#end
				</td>
			</tr>
			<!-- vertical spacing -->
			<tr>
				<td class="" width="100%" height="10" style="font-size: 1px; line-height: 10px;"></td>
			</tr>
		#end
		<tr>
			<td class="mobileShow-right" width="100%" height="15" style="width:100%; height:15px;">
				<table class="mobileShow-right" align="left" cellspacing="0" cellpadding="0" border="0" >
					<tbody>
						<tr>
							<td width="100%" align="left" height="15" style="width:100%; height:15px;">
								<a href="http://rd.BookingBuddy.com/?r=i7185119n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&tid=$destination_id" style="text-decoration:none;" target="_blank">
									<span style="font-family: $font-family; font-size: 13px; color:#26A6D1; border-bottom: 1px solid #26A6D1;">See more ${arr_city_name_short} hotels</span>
								</a>
							</td>
						</tr>
					</tbody>
				</table>
			</td>
		</tr>
	#end
	<!-- vertical spacing -->
	<tr>
		<td width="100%" height="40" style="font-size: 1px; line-height: 10px;"></td>
	</tr>
#end
## macro for more fares
#macro(macro_fare, $fare, $isMobileHide)
	#if ($isMobileHide == "true")
		#set($className = "mobileHide")
	#else
		#set($className = "")
	#end
	<table  class=$className width="226" height="150" bgcolor="#ffffff" align="left"  cellspacing="0" cellpadding="0" style="bgcolor: #ffffff; width: 226px; height: 150px; border-left: $border-spec; border-right: $border-spec; border-top: $border-spec;">
		<tbody>
			<!-- fare arrival city name -->
			<tr >
				<td height="38" align="center" style="font-family: $font-family; font-size: 20px; color: $font-color-black; padding-top: 3px;">
					$fare.arrivalAirportDisplay
				</td>
			</tr>
			<!-- fare price -->
			<tr>
				<td height="45" align="center"  style="font-family: $font-family; font-size: 28px; color: $font-color-black; ">
					$fare.priceFormatted <span class="mobileHide" style="font-size: 18px;">$fare.flightType</span>
				</td>
			</tr>
			<!-- "See Details" -->
			<tr>
				<td width="100%" height="50" align="left" border="0" style="width:100%; height: 50px;">
					<table  width="55" height="5" cellspacing="0" cellpadding="0" border="0" align="left" style="width:55px; height:5px;" >
						<tr>
							<td width="55" height="5" align="left" style="font-size: 1px; line-height: 1px;">&nbsp;</td>
						</tr>
					</table>
					<table width="125" height="50" cellspacing="0" cellpadding="0" border="0" align="left" style="width:125px; height:50px;" >
						<tr>
							<td width="125" height="35" align="left" style="width: 125px; height: 35px; ">
								<a href="http://rd.bookingbuddy.com/?r=i3993194n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&fare_id=$fare.fareId&departure_city=$feature_fare_departure_code&arrival_city=$fare.arrivalAirportCode${source}_morefares_${nl_date_numeric}&ns=1" style="text-decoration:none;" target="_blank">
									<img src=$image_basic_url/$see_details_btn_desktop width="125" height="35"  border="0" style="display:block; width:125; height: 35px; " />
								</a>
							</td>
						</tr>
					</table>
				</td>
			</tr>
			<tr>
				<td class="" width="100%" height="10" style="font-size: 1px; line-height: 10px; border-left: $border-spec; border-right: $border-spec; border-bottom: $border-spec;"></td>
			</tr>
		</tbody>
	</table>
#end
#macro(macro_more_fares, $more_fares)
	#if ($more_fares && $more_fares.size() > 0)
		<!-- More Fares Title -->
		<tr>
			<td width="100%" heidth="35" style="width:100%; height:35px;">
				<table width="390" align="left" style="width:390px;" border="0" align="left" cellpadding="0" cellspacing="0" >
					<tbody>
						<tr>
							<td width="100%" height="35" bgcolor="#3baed5" align="left" style="width: 100%; height:35px; font-family: $font-family; color: $font-color-white; font-size: 20px; padding-left: 5px;">
								More Low Fares from ${dep_city_name_short}
							</td>
						</tr>
					</tbody>
				</table>
			</td>
		</tr>
		## When there are two or three deals, only show two
		#if ($more_fares.size() < 6)
			##There are less than four deals, show the two in one row
			<tr> 
				<td width="100%" height="150" style="height: 150px; width: 100%; " >
					#set($count = 0)
					#foreach ($fare in $more_fares)
						#if ($count < 3)
							## only show 3 deals at most
							#if ($count == 2)
								#macro_fare($fare, "true")	
							#else
								#macro_fare($fare, "false")
							#end
							#if ($count < 2)
								<!-- horizontal spacing -->
								<table width="5" height="5" cellspacing="0" cellpadding="0" border="0" align="left" style="width:5px; height:5px;">
									<tbody>
										<tr>
											<td width="5" height="5" style="font-size: 1px; line-height: 1px;">&nbsp;</td>
										</tr>
									</tbody>
								</table>
							#end
						#end
						#set($count = $count + 1)
					#end
				</td>
			</tr>
		#else
			## When there are four deals in total
			<!-- Row 1 -->
			<tr> 
				<td width="100%" height="150" style="height: 150px; width: 100%; " >
				#set($count = 0)
				#foreach ($fare in $more_fares)
					#if ($count < 3)
						#if ($count == 2)
							#macro_fare($fare, "true")	
						#else
							#macro_fare($fare, "false")
						#end
						#if ($count < 2 )
							<!-- horizontal spacing -->
							<table width="5" height="5" cellspacing="0" cellpadding="0" border="0" align="left" style="width:5px; height:5px;">
								<tbody>
									<tr>
										<td width="5" height="5" style="font-size: 1px; line-height: 1px;">&nbsp;</td>
									</tr>
								</tbody>
							</table>
						#end
						#set($count = $count + 1)
					#end
				#end
				</td>
			</tr>
			<!-- vertical spacing -->
			<tr>
				<td width="100%" height="10" bgcolor="#f6f6f6"  style="width: 100%; height:10px; bgcolor:#f6f6f6;"></td>
			</tr>
			<!-- Row 2 -->
			<tr> 
				<td width="100%" height="150" style="height: 150px; width: 100%; ">
				#set($count = 0)
				#foreach ($fare in $more_fares)
					#if ($count >= 3)
						#if ($count == 5)
							#macro_fare($fare, "true")	
						#else
							#macro_fare($fare, "false")
						#end
						#if ($count < 5)
							<!-- horizontal spacing -->
							<table width="5" height="5" cellspacing="0" cellpadding="0" border="0" align="left" style="width:5px; height:5px;">
								<tbody>
									<tr>
										<td width="5" height="5" style="font-size: 1px; line-height: 1px;">&nbsp;</td>
									</tr>
								</tbody>
							</table>
						#end
					#end
					#set($count = $count + 1)
				#end
				</td>
			</tr>
		#end
		<!-- vertical spacing -->
		<tr>
			<td  width="100%" height="10" style="font-size: 1px; line-height: 10px;"></td>
		</tr>
		<tr>
			<td width="100%" height="15" align="left" style="width:100%; height:15px;">
				<table class="mobileShow" style="display: none; line-height: 0; font-size:0px; max-height: 0px;" align="left" cellspacing="0" cellpadding="0" border="0" >
					<tbody>
						<tr class="mobileShow-wAll-h15-f13" style="font:0;">
							<td class="mobileShow-wAll-h15-f13" width="0" style=" width:0px; height:15px; max-height: 0; font-family: $font-family; font-size: 0px; color:$font-color-black;  ">
								All fares shown are round trip.
							</td>
						</tr>
					</tbody>
				</table>
				<table class="mobileShow-right" align="left" cellspacing="0" cellpadding="0" border="0" >
					<tbody>
						<tr>
							<td width="100%" align="right" height="15" style="width:100%; height:15px;">
								<a href="http://rd.bookingbuddy.com/?r=i3993200n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&departure_city=${feature_fare.departureAirportCode}" style="text-decoration:none;" target="_blank">
									<span style="font-family: $font-family; font-size: 13px; color:#26A6D1; border-bottom: 1px solid #26A6D1;">See more flights from ${dep_city_name_short}</span>
								</a>
							</td>
						</tr>
					</tbody>
				</table>
			</td>
		</tr>
		<!-- vertical spacing -->
		<tr>
			<td class="h40" width="100%" height="50" style="font-size: 1px; line-height: 10px;"></td>
		</tr>
	#end
#end

MAIL FROM:<b-${tracking_code}-${mailing_id}-${newsletter_id}-${timestamp}@${sending_domain}>
RCPT TO:<${email_address}>
DATA
From: "${from_name}" <${from_address}>
To: "${greeting}" <${email_address}>
Subject: ${subject}
Reply-To: "${reply_to_name}" <${reply_to_address}>
Errors-To: b-${tracking_code}-${mailing_id}-${newsletter_id}-${timestamp}@${sending_domain}
Message-ID: <m-${tracking_code}-${mailing_id}-${newsletter_id}-${timestamp}@${sending_domain}>
List-ID: "${from_name}" <${from_address}>
X-RPCampaign: STM${site_abbreviation}${product_abbreviation}${newsletter_id}${timestamp}
Precedence: bulk
MIME-Version: 1.0
Content-Type: text/html; charset=utf-8
Content-Transfer-Encoding: quoted-printable

<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">	
<html>
	<head>
		<meta />
		<title></title>
		<link rel="stylesheet" type="text/css" href="http://c.slimg.com/nlot/${tracking_code}/${newsletter_id}/${nltv}/bbnl_generic.css" />
	</head>
	<body topmargin="0" leftmargin="0" marginheight="0" marginwidth="0">
		<style type="text/css">
			table { border-collapse:collapse; mso-table-lspace:0pt; mso-table-rspace:0pt; } 
			@media only screen and (max-device-width: 480px) {

				*[class~=mobileHide] { 
					display:none !important;
					font-size: 0 !important;
					max-height:0 !important;
					font-size: 0 !important;
					line-height: 0 !important;
					width: 0px !important;
					height: 0px !important;
					mso-hide: all !important;
					visibility:hidden !important;
				}
				*[class~=mobileShow] { 
					display:block !important;
					font-size: -1 !important;
					max-height:none !important;
					line-height: 1 !important;
				}
				*[class~=mobileShow-table-cell] { 
					display:table-cell !important;
					font-size: -1 !important;
					max-height:none !important;
					line-height: 1 !important;
				}
				*[class~=mobileShow-w188] { 
					display:block !important;
					font-size: -1 !important;
					max-height:none !important;
					line-height: 1 !important;
					width: 188px !important;
				}
				*[class~=mobileShow-w390] { 
					display:block !important;
					font-size: -1 !important;
					max-height:none !important;
					line-height: 1 !important;
					width: 390px !important;
				}
				*[class~=mobileShow-w390-h35-f20] { 
					display:block !important;
					font-size: 20px !important;
					max-height:none !important;
					line-height: 1.5 !important;
					width: 390px !important;
					height: 35px !important;
				}
				*[class~=mobileShow-w390-h35-f20-lp5] { 
					display:block !important;
					font-size: 20px !important;
					max-height:none !important;
					line-height: 1.5 !important;
					width: 390px !important;
					height: 35px !important;
					padding-left: 5px !important;
				}
				*[class~=mobileShow-wAll-h40] { 
					display:block !important;
					font-size: -1 !important;
					max-height:none !important;
					line-height: 1 !important;
					width: 100% !important;
					height: 40px !important;
				}
				*[class~=mobileShow-wAll-h35-f20-lp5] { 
					display:block !important;
					font-size: 20px !important;
					max-height:none !important;
					line-height: 1 !important;
					width: 100% !important;
					height: 35px !important;
					padding-left: 5px !important;
				}
				*[class~=mobileShow-w188-h27] { 
					display:block !important;
					font-size: -1 !important;
					max-height:none !important;
					line-height: 1 !important;
					width: 188px !important;
					height: 27px !important;
				}
				*[class~=mobileShow-w60-h5] { 
					display:block !important;
					font-size: -1 !important;
					max-height:none !important;
					line-height: 1 !important;
					width: 60px !important;
					height: 5px !important;
				}
				*[class~=mobileHide-w130-h40] { 
					display:block !important;
					font-size: -1 !important;
					max-height:none !important;
					line-height: 1 !important;
					width: 130px !important;
					height: 40px !important;
				}
				*[class~=mobileShow-w130-h40] { 
					display:block !important;
					font-size: -1 !important;
					max-height:none !important;
					line-height: 1 !important;
					width: 130px !important;
					height: 40px !important;
				}
				*[class~=mobileShow-w247-h155] { 
					display:block !important;
					font-size: -1 !important;
					max-height:none !important;
					line-height: 1 !important;
					width: 247px !important;
					height: 155px !important;
				}
				*[class~=mobileShow-w200] { 
					display:block !important;
					font-size: -1 !important;
					max-height:none !important;
					line-height: 1 !important;
					width: 200px !important;
				}
				*[class~=mobileShow-w480] { 
					display:block !important;
					font-size: -1 !important;
					max-height:none !important;
					line-height: 1 !important;
					width: 480px !important;
				}
				*[class~=mobileShow-w480-h30-topborder-bottomborder] { 
					display: block !important;
					font-size: -1 !important;
					max-height:none !important;
					line-height: 1 !important;
					width: 480px !important;
					height: 30px !important;
					border-top: $border-spec !important; 
					border-bottom: $border-spec !important;
				}
				*[class~=mobileShow-w480-h32-table] { 
					display: table !important;
					font-size: -1 !important;
					max-height:none !important;
					line-height: 1 !important;
					width: 480px !important;
					height: 32px !important;
				}
				*[class~=mobileShow-w160-h30-table] { 
					display: table !important;
					font-size: -1 !important;
					max-height:none !important;
					line-height: 1 !important;
					width: 160px !important;
					height: 30px !important;
				}
				*[class~=mobileShow-w160-h8] { 
					display:block !important;
					font-size: -1 !important;
					max-height:none !important;
					line-height: 1 !important;
					width: 160px !important;
					height: 8px !important;
				}
				*[class~=mobileShow-w233-h155] { 
					display:block !important;
					font-size: -1 !important;
					max-height:none !important;
					line-height: 1 !important;
					width: 233px !important;
					height: 155px !important;
				}
				*[class~=mobileShow-w147-h45-f18-tp10] { 
					display:block !important;
					font-size: 18px !important;
					max-height:none !important;
					line-height: 1 !important;
					width: 247px !important;
					height: 45px !important;
					padding-top: 10px !important;
				}
				*[class~=mobileHide-h30-f28-bp10] { 
					display:block !important;
					font-size: 28px !important;
					max-height:none !important;
					line-height: 1 !important;
					width: 100% !important;
					height: 30px !important;
					padding-bottom: 10px !important;
				}
				*[class~=mobileShow-w480-h30] { 
					display:block !important;
					font-size: -1 !important;
					max-height:none !important;
					line-height: 1 !important;
					width: 480px !important;
					height: 30px !important;
				}
				*[class~=mobileShow-w480-h10] { 
					display:block !important;
					font-size: -1 !important;
					max-height:none !important;
					line-height: 1 !important;
					width: 480px !important;
					height: 10px !important;
				}
				*[class~=mobileShow-w480-f15] { 
					display:block !important;
					font-size: 15px !important;
					max-height:none !important;
					line-height: 1 !important;
					width: 480px !important;
				}
				*[class~=mobileShow-left] { 
					display:block !important;
					font-size: -1 !important;
					max-height:none !important;
					line-height: 1 !important;
					padding-left: 10px !important;
				}
				*[class~=mobileShow-right] { 
					display:block !important;
					font-size: -1 !important;
					max-height:none !important;
					line-height: 1 !important;
					float: right !important;
				}	
				*[class~=mobileShow-image-w5] { 
					display:block !important;
					max-height:none !important;
					width: 5px !important;
				}
				*[class~=mobileShow-image-w30] { 
					display:block !important;
					max-height:none !important;
					width: 30px !important;
				}
				*[class~=mobileShow-image-w125] { 
					display:block !important;
					max-height:none !important;
					width: 125px !important;
				}
				*[class~=mobileShow-image-w188] { 
					display:block !important;
					max-height:none !important;
					width: 188px !important;
				}
				*[class~=mobileShow-image-w480] { 
					display:block !important;
					max-height:none !important;
					width: 480px !important;
				}
				*[class~=mobileShow-image-w480-h90] { 
					display:block !important;
					max-height:none !important;
					width: 480px !important;
					height: 90px !important;
				}
				*[class~=mobileShow-f15] { 
					display:block !important;
					font-size: 15px !important;
					max-height:none !important;
					line-height: 1 !important;
				}
				*[class~=mobileShow-f15-table] { 
					display:table !important;
					font-size: 15px !important;
					max-height:none !important;
					line-height: 1 !important;
				}
				*[class~=mobileShow-f16] { 
					display:block !important;
					font-size: 16px !important;
					max-height:none !important;
					line-height: 1 !important;
				}
				*[class~=mobileShow-f16-w200] { 
					display:block !important;
					font-size: 16px !important;
					max-height:none !important;
					line-height: 1 !important;
					width: 200px !important;
				}
				*[class~=mobileShow-f16-bold-left] { 
					display:block !important;
					font-size: 16px !important;
					max-height:none !important;
					line-height: 1 !important;
					font-weight: bold !important;
					text-align: left !important;
					padding-left: 10px !important;
					padding-right: 10px !important;
					padding-top: 20px !important;
				}
				*[class~=mobileShow-f13] { 
					display:block !important;
					font-size: 13px !important;
					max-height:none !important;
					line-height: 1 !important;
				}
				*[class~=mobileShow-f13-left] { 
					display:block !important;
					font-size: 13px !important;
					max-height:none !important;
					line-height: 1 !important;
					padding-left: 10px !important;
				}
				*[class~=mobileShow-f20-left] { 
					display:block !important;
					font-size: 20px !important;
					max-height:none !important;
					line-height: 1 !important;
					text-align: left !important;
					padding-left: 10px !important;
					padding-right: 10px !important;
					padding-top: 10px !important;
				}
				*[class~=mobileShow-f30-cOrange-left] { 
					display:block !important;
					font-size: 30px !important;
					max-height:none !important;
					color: #e97f0a !important;
					line-height: 1 !important;
					text-align: left !important;
					padding-left: 10px !important;
					padding-right: 10px !important;
					padding-top: 10px !important;
				}
				*[class~=mobileShow-f30] { 
					display:block !important;
					font-size: 30px !important;
					max-height:none !important;
					line-height: 1 !important;
				}
				*[class~=mobileShow-h5-topborder] { 
					display:block !important;
					font-size: 13px !important;
					max-height:none !important;
					line-height: 1 !important;
					height: 5px !important;
					border-top: $border-spec !important;
				}		
				*[class~=mobileShow-h20] { 
					display:block !important;
					font-size: 1px !important;
					max-height:none !important;
					line-height: 1 !important;
					height: 20px !important;
				}
				*[class~=mobileShow-h35] { 
					display:block !important;
					font-size: 1px !important;
					max-height:none !important;
					line-height: 1 !important;
					height: 35px !important;
				}
				*[class~=mobileShow-wAll-h15-f13] { 
					display:block !important;
					font-size: 13px !important;
					max-height:none !important;
					line-height: 1 !important;
					height: 15px !important;
					width: 100% !important;
				}
				*[class~=wAll] { width: 100% !important; }
				*[class~=w480] { width: 480px !important; }
				*[class~=w250] { width: 250px !important; }
				*[class~=w233] { width: 233px !important; }
				*[class~=w247] { width: 247px !important; }
				*[class~=w235] { width: 235px !important; }
				*[class~=w150] { width: 150px !important; }
				*[class~=w10] { width: 10px !important; }
				*[class~=h40] { height: 40px !important; }
				*[class~=h80] { height: 80px !important; }
				*[class~=h155] { height: 155px !important; }
				*[class~=h165] { height: 165px !important; }
				*[class~=h320] { height: 320px !important; }
				*[class~=h335] { height: 335px !important; }
			}
		</style>
		<table width="100%" cellpadding="0" cellspacing="0" border="0">
			<tbody>
				<td align="left" bgcolor=$bgcolor>
					<img src="http://i.slimg.com/nlot/${tracking_code}/${newsletter_id}/${nltv}/s.gif" border="0" hspace="0" vspace="0" width="1" height="1" align="right" />
					<table class="w480" width="700" style="width: 700px" border="0" cellpadding="0" cellspacing="0" bgcolor=$bgcolor align="center">
						<tbody>
							<!-- snippet -->
							<tr>
								<td align="center" >
									<table cellpadding="0" cellspacing="0" border="0" align="left">
										<tr>
											<td align="left" style="font: 12px Arial, sans-serif; color: #444444;">New <a href="http://rd.bookingbuddy.com/?r=i3993194n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&fare_id=${feature_fare.fareId}&departure_city=${feature_fare.departureAirportCode}&arrival_city=${feature_fare.arrivalAirportCode}${source}_featfare_${nl_date_numeric}&ns=1"><u>${dep_city_name_short} to ${arr_city_name_short}</u></a> Fare | See all <a href="http://rd.bookingbuddy.com/?r=i3993200n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&departure_city=${feature_fare.departureAirportCode}">${dep_city_name_short}</a> fares | <a href="http://rd.bookingbuddy.com/?r=i3961415n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&email=${email_encoded}&mode=prefs${source}">Update my Alert</a>
											</td>
										</tr>
									</table>
								</td>
							</tr>
							<!-- header desktop -->
							<tr>
								<td >
									<table cellspacing="0" cellpadding="0" border="0"  width="100%" style="width:100%;">
										<tbody>
											<tr>
												<td width=100% height=30 align="left" style="height:30px; font-family:$font-family; font-size:15px;color:$font-color-black; ">
													<table   align="right" cellspacing="0" cellpadding="0" border="0">
														<tr>
															<td align="left" width="100%" style="width:100%;  font-family:$font-family; font-size:15px;color:$font-color-black; padding-right: 5px;">
																${dep_city_name_short} Fare Alert  &nbsp;|&nbsp;  ${nl_date}
															</td>
														</tr>
													</table>
												</td>
											</tr>
											<tr>
												<td   width="100%" height="35" align="left" bgcolor="#ffffff" style="width: 100%; height:35px;bgcolor:#ffffff;">
													<!-- logo -->
													<table   align="left" cellspacing="0" cellpadding="0" border="0">
														<tr>
															<td  align="left" width="150" height="21" style="width:150px; height:21px; padding-left: 10px;">
																<a href="http://rd.bookingbuddy.com/?r=i3961363n${newsletter_id}&u=${tracking_code}&nltv=${nltv}">
																	<img  src=$image_basic_url/BB_Logo.png alt="type-icon" width="150" height="21" border="0" style="display:block; "/>
																</a>
															</td>
														</tr>
													</table>
													<!-- nav -->
													<table class="w250"  width="350" cellspacing="0" cellpadding="0" border="0" align="right">
														<tr>
															<td  align="center"><a style="text-decoration:none; " href="http://rd.bookingbuddy.com/?r=i3961394n${newsletter_id}&u=${tracking_code}&nltv=${nltv}"><span style="text-decoration:none;font-weight:bold; font-size: 15px; font-family:$font-family; color:$font-color-black;" >Flights</span></a></td>
															<td  align="center"><a style="text-decoration:none; " href="http://rd.bookingbuddy.com/?r=i3961395n${newsletter_id}&u=${tracking_code}&nltv=${nltv}"><span style="text-decoration:none;font-weight:bold; font-size: 15px; font-family:$font-family; color:$font-color-black;">Hotels</span></a></td>
															<td  align="center"><a style="text-decoration:none; "  href="http://rd.bookingbuddy.com/?r=i3961399n${newsletter_id}&u=${tracking_code}&nltv=${nltv}"><span style="text-decoration:none;font-weight:bold; font-size: 15px; font-family:$font-family;color:$font-color-black;">Vacations</span></a></td>
															<td  class="mobileHide" align="center"><a style="text-decoration:none; " href="http://rd.bookingbuddy.com/?r=i3961403n${newsletter_id}&u=${tracking_code}&nltv=${nltv}"><span style="text-decoration:none;font-weight:bold; font-size: 15px; font-family:$font-family;color:$font-color-black;">Cars</span></a></td>
															<td  class="mobileHide" align="center"><a style="text-decoration:none; " href="http://rd.bookingbuddy.com/?r=i3961405n${newsletter_id}&u=${tracking_code}&nltv=${nltv}"><span style="text-decoration:none;font-weight:bold; font-size: 15px; font-family:$font-family; color:$font-color-black;">Cruises</span></a></td>
														</tr>
													</table>
												</td>
											</tr>
										</tbody>
									</table>
								</td>
							</tr>
							<!-- vertical spacing -->
							<tr>
								<td width="100%" height="35" style="font-size: 1px; line-height: 10px;"></td>
							</tr>
							<!-- main content -->
							<tr>
								<td>
									<!-- ad -->
									<table class="mobileHide" width="145" height="560" cellspacing="0" cellpadding="0" border="0" align="right">
										<tbody>
											<!-- vertical spacing -->
											<tr>
												<td class="mobileHide" width="100%" height="10" style="font-size: 1px; line-height: 10px;"></td>
											</tr>
											<tr>
												<td width="145" style="width: 145px; height:550px;" valign="top" style="padding: 0 0 0 3px;">
													<a href="http://ad.doubleclick.net/N5349/jump/ta.bb.com.email/bb_city_to_city_route_alerts;dcove=r;sz=160x600;nid=${newsletter_id};${dart_tags}${dart_origin_tags}${dart_destination_tags};tile=1;ord=${dart_ord}?" >
														<img class="mobileHide"  width="145"  style="width: 145px; display:block;" src="http://ad.doubleclick.net/N5349/ad/ta.bb.com.email/bb_city_to_city_route_alerts;dcove=r;sz=160x600;nid=${newsletter_id};${dart_tags}${dart_origin_tags}${dart_destination_tags};tile=1;ord=${dart_ord}?" alt="" border="0" />
													</a>
												</td>
											</tr>
										</tbody>
									</table>
									<!-- main content -->
									<table class="w480" width="500" cellspacing="0" cellpadding="0" border="0" align="left">
										<tbody>
											<!-- feature fare -->
											#macro_feature_fare($feature_fare_title, $feature_fare_departure, $feature_fare_destination, $feature_fare_price , $feature_fare_flight_type, $feature_fare_flight_type, $feature_fare_airlinetext, $feature_fare_image_url, $feature_fare_destination_code)
											<!-- hot tip -->
											#if ($is_engaged == "true")
												#macro_hot_tip($hot_tip_title, $hot_tip_url, $hot_tip_image_url ,$hot_tip_image_alt, $hot_tip_title, $read_more_image)
											#end
											<!-- low fares -->
											#macro_nearby_fares($nearby_fares)
											<!-- Hotel Deals -->
											<tr>
												<td class="w480" width="500" style="width: 500px;">
													<table class="w480" width="500" cellspacing="0" cellpadding="0" border="0" align="left" style="width: 500px;">
														#macro_hotel_deals($deals)	
													</table>
												</td>
											</tr>
										</tbody>
									</table>
								</td>
							</tr>
							<!-- More low fares -->
							<tr>
								<td class="w480" width="100%" style="width: 100%;">
									<table class="w480" width="100%" cellspacing="0" cellpadding="0" border="0" align="left" style="width: 100%;">
										<!-- More low fares -->
										#macro_more_fares($more_fares)
									</table>
								</td>
							</tr>	
							<!-- Searching widget -->
							<tr>
								<td width="100%" height="35" align="left" style="width: 100%; height:18px; font-family: $font-family; color: $font-color-black; font-size: 18px; padding-left: 5px;">
									Find the Deal You're Looking For
								</td>
							</tr>
							<!-- vertical spacing -->
							<tr>
								<td class="" width="100%" height="5" style="font-size: 1px; line-height: 10px;"></td>
							</tr>
							<tr>
								<td class="w480" width="700" height="90" style="width:700px; height: 90px; display:block;">
									<table class="w480" width="700" cellspacing="0" cellpadding="0" border="0" align="left">
										<tbody>
											<tr>
												<td width="313" height="90" style="width: 313px; height:90px;" >
													<a href="http://rd.bookingbuddy.com/?r=i3961394n${newsletter_id}&u=${tracking_code}&nltv=${nltv}${source}_widget_${feature_fare.departureAirportCode}_${nl_date_numeric}&ns=1" style="text-decoration:none;" target="_blank">
														<img src=$image_basic_url/$search_widget_1  alt="" width="313" border="0" style="display:block; width:313px; height: 90px;">
													</a>	
												</td>
												<td class="mobileHide" width="220" height="90" style="width: 220px; height:90px;" >
													<a href="http://rd.bookingbuddy.com/?r=i3961394n${newsletter_id}&u=${tracking_code}&nltv=${nltv}${source}_widget_${feature_fare.departureAirportCode}_${nl_date_numeric}&ns=1" style="text-decoration:none;" target="_blank">
														<img src=$image_basic_url/$search_widget_2  alt="" width="220" border="0" style="display:block; width:220px; height: 90px;">
													</a>	
												</td>
												<td width="167" height="90" style="width: 167px; height:90px;" >
													<a href="http://rd.bookingbuddy.com/?r=i3961394n${newsletter_id}&u=${tracking_code}&nltv=${nltv}${source}_widget_${feature_fare.departureAirportCode}_${nl_date_numeric}&ns=1" style="text-decoration:none;" target="_blank">
														<img src=$image_basic_url/$search_widget_3  alt="" width="167" border="0" style="display:block; width:167px; height: 90px;">
													</a>	
												</td>
											</tr>
										</tbody>
									</table>
								</td>
							</tr>
							<!-- vertical spacing -->
							<tr>
								<td class="h40" width="700" height="50" style="font-size: 1px; line-height: 10px;" ></td>
							</tr>
							<!-- footer -->
							<tr>
								<td class="w480" width="700" height="25px" bgcolor=$bgcolor>
									<table>
										<tbody>
											<tr>
												<td class="w480" width="700" height="25px" bgcolor=$bgcolor>
													<table class="w480" width="700" cellspacing="0" cellpadding="0" border="0" align="left" >
															<tr>
																<td align="center" style="border-right: $border-spec; border-color: #26A6D1;">
																	<a style="text-decoration:none; " href="http://rd.bookingbuddy.com/?r=i3961415n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&email=${email_encoded}&mode=prefs${source}"><span style="text-decoration:none; font-family:$font-family;font-size:12px; color:#26A6D1;">Email Preferences</span>
																	</a>
																</td>
																<td align="center" style="border-right: $border-spec; border-color: #26A6D1;">
																	<a style="text-decoration:none; " href="http://rd.bookingbuddy.com/?r=i3961415n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&email=${email_encoded}&mode=prefs${source}"><span style="text-decoration:none; font-family:$font-family;font-size:12px; color:#26A6D1;">Unsubscribe</span>
																	</a>	
																</td>
																<td align="center" style="border-right: $border-spec; border-color: #26A6D1;">
																	<a style="text-decoration:none; " href="http://rd.bookingbuddy.com/?r=i3961435n${newsletter_id}&u=${tracking_code}&nltv=${nltv}${source}" ><span style="text-decoration:none; font-family:$font-family;font-size:12px; color:#26A6D1;">Term of Use</span>
																	</a>
																</td>
																<td align="center" style="border-right: $border-spec; border-color: #26A6D1;">
																	<a style="text-decoration:none; " href="http://rd.bookingbuddy.com/?r=i3961436n${newsletter_id}&u=${tracking_code}&nltv=${nltv}${source}"><span style="text-decoration:none; font-family:$font-family;font-size:12px; color:#26A6D1;">Privacy Policy</span>
																	</a>
																</td>
																<td align="center">
																	<a style="text-decoration:none; " href="http://rd.bookingbuddy.com/?r=i3961430n${newsletter_id}&u=${tracking_code}&nltv=${nltv}${source}" ><span style="text-decoration:none; font-family:$font-family;font-size:12px; color:#26A6D1;">Feedback</span>
																	</a>
																</td>
															</tr>
													</table>
												</td>
											</tr>
										</tbody>
									</table>
								</td>
							</tr>
							<!-- vertical spacing -->
							<tr>
								<td class="h5" width="100%" height="10" style="font-size: 1px; line-height: 10px;" ></td>
							</tr>
							<!-- some words -->
							<tr>
								<td width="700" bgcolor="#f6f6f6">
									 <table  width="100%" border="0" cellspacing="0" cellpadding="0" align="center">
										<tr>
										  <td class="fineprint">
											<span class="ftrtext">
											<p style="font-size: 10px; font-family:$font-family; color: $font-color-black;">
												You received this email because you subscribed as: ${email_address}
												.This is a commercial newsletter that contains advertisements from
												travel suppliers and agencies. If you no longer wish to receive this
												newsletter, please <a style="text-decoration:none; " href="http://rd.bookingbuddy.com/?r=i273888n${newsletter_id}&u=${tracking_code}&nltv=${nltv}&email=${email_encoded}&mode=prefs${source}" ><span style="color: $font-color-black;text-decoration: none;"><u>unsubscribe here</u></span></a>.
											</p>
											<p style="font-size: 10px;font-family:$font-family; color: $font-color-black;">
											BookingBuddy.com is a travel search service and information provider. We
											do not sell travel products or services. We help you search for travel
											products/services from third-party. However, the <span style="font-size: 8px;">3<sup style="font-size: 6px;">rd</sup></span> party suppliers
											that supply travel products and services may change the offers for variety of reasons,
											and we cannot therefore guarantee any information in their offers, which change from time to time.
											We are not responsible for <span style="font-size: 8px;">3<sup style="font-size: 6px;">rd</sup></span> party products, services or site content
											</p>
											<p style="font-size: 10px; font-family:$font-family;color: $font-color-black;">
											Copyright &copy; 2005-${current_year} Smarter Travel Media LLC. All Rights
											Reserved. BookingBuddy is a trademark of BookingBuddy.com, Inc., a
											wholly-owned subsidiary of Smarter Travel Media LLC.
											</p>
											<p style="font-size: 10px;font-family:$font-family; color: $font-color-black;">
											<a href="http://www.smartertravelmedia.com" style="text-decoration:none;color: $font-color-black;"><span style="text-decoration:none;"><u>Smarter Travel Media LLC</u></span></a> | 226 Causeway Street | 3rd Floor | Boston, MA 02114 | 617.886.5555
											</p>
											</span>
										  </td>
										</tr>
	  								</table>
								</td>
							</tr>
						</tbody>
					</table>
				</td>
			</tbody>
		</table>
	</body>
</html>			